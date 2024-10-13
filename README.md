# DREAM-TEAM---PROJECT-1

## Team Name
MIST 4610: 29704 - Dream Team

## Team Members
1. Flynn Duel 
2. Anna Pachon
3. Jeremiah Doherty
4. Geetika Polkam
5. Krutee Pillay

## Problem Description
The task at hand is to develop a database for a record store that will help with day to day activities. The main entity in this model is record, which represents the music albums in the store. Record has a relationship with other important entities such as artists, customers, promotions etc to help with running the store. This system is designed to help define the relationships between entities as well as be populated with sample data. Queries will be used to analyze the sample data.

## Data Model

![project1dbpic](https://github.com/user-attachments/assets/328c88e4-59ad-4e66-9eb4-57fdf2dbd398)



## Queries
### Complex 1
<img width="510" alt="Screenshot 2024-10-13 at 3 58 51 PM" src="https://github.com/user-attachments/assets/2a261965-8bba-4352-8555-7aa209bc82e4">

### Complex 2
<img width="485" alt="Screenshot 2024-10-13 at 4 00 27 PM" src="https://github.com/user-attachments/assets/6b6fed06-57c1-41e4-9aac-8bf2c02d4a43">

### Complex 3
This query lists each employee based on the most orders fulfilled to the least amount of orders fulfilled

<img width="596" alt="Screenshot 2024-10-13 at 4 01 52 PM" src="https://github.com/user-attachments/assets/64d0231e-8791-428f-a12a-636f13f58383">

**Why is this important for management? -** Understanding how many orders each employee has fulfilled is important for management because it allows management to make decisions based off of employee performance. It allows for management to create better systems and differentiate work more efficiently either by getting rid of unnecessary employees or making sure certain employees step up their work. It will show management which employees are doing their jobs well and which ones are slacking. 

### Complex 4
new query from anna (could jeremiah run and replace with picture)

shows how many records from each genre have recieved promotions:

SELECT genrename, COUNT(DISTINCT record.idrecord) AS Promotion_amount

FROM genre

JOIN record ON genre.idgenre = record.genre_idgenre

JOIN promotion_has_record ON record.idrecord = promotion_has_record.record_idrecord

JOIN promotion ON promotion_has_record.promotion_idpromotion = promotion.idpromotion

GROUP BY genre.genrename;

### Complex 5
new query from anna (could jeremiah run and replace with picture):
show the name, order date, and order ID of customers that have placed an order that has not yet been shipped

SELECT customer.firstname, customer.lastname, idorder, orderdate

FROM customer, order

JOIN order ON customer.idcustomer = order.customer_idcustomer

WHERE NOT EXISTS (
    SELECT shipped_date
    FROM shipment
    WHERE shipment.idshipment = order.shipment_idshipment);
### Complex 6

### Simple 1
<img width="566" alt="Screenshot 2024-10-13 at 4 04 15 PM" src="https://github.com/user-attachments/assets/c67b472e-7d06-49e2-9a04-b98221da219a">

### Simple 2
new query from anna (could jeremiah run and replace with picture)
shows all of the promotions that were over a week long and how long they lasted

SELECT promotiondescription, startdate, enddate, DATEDIFF(enddate, startdate) AS duration

FROM promotion

WHERE DATEDIFF(enddate, startdate) > 7;

### Simple 3
This query lists the number of orders, in descending order, placed in each state.

<img width="500" alt="Screenshot 2024-10-13 at 4 22 00 PM" src="https://github.com/user-attachments/assets/11c2fde8-cd77-4118-9f71-36145e1c858a">

**Why is this important for management? -** Management needs to be able to determine what states are doing the best from a sales standpoint. This query allows management to track where most of their sales are coming from and then make the appropriate decisions regarding the best way to approach selling in each state. One state may have many sales while another is doing really well; this query will allow management to decide on where they want to focus their marketing. It will also further aid management in the decision of if they want to pull out of a certain state that is not producing the amount of sales it needs to be producing. 
### Simple 4
