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

## Data Model
<img width="583" alt="Screenshot 2024-10-13 at 3 50 38 PM" src="https://github.com/user-attachments/assets/4ee3a424-21e4-4571-8d28-07ec536c393b">


## Queries
### Complex 1
SELECT artist.artistname, SUM(inventory.quantityinstock) AS remaining_inventory FROM inventory

JOIN supplier_has_record 
ON inventory.supplier_has_record_record_idrecord = supplier_has_record.record_idrecord

JOIN record ON supplier_has_record.record_idrecord = record.idrecord

JOIN artist ON record.artist_idartist = artist.idartist

GROUP BY artist.artistname
ORDER BY remaining_inventory DESC;

### Complex 2

### Complex 3

### Complex 4

### Complex 5

### Complex 6

### Simple 1

### Simple 2

### Simple 3

### Simple 4
