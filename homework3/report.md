##  Homework 3
####  Merci Magallanes and John Scott


###  MongoDB Database Exercise

Use single queries for these, meaning you may NOT execute one query and then execute a second, third, fourth, ....., n'th query to determine maximums, minimums or counts.

1.  What are the different collections in the Northwind database?
>  \> use Northwind  
switched to db Northwind  
\> show collections  
categories  
customers  
employee-territories  
northwind  
order-details  
orders  
products  
regions  
shippers  
suppliers  
territories

2.  How many documents are in the "categories" collection?
>  \> db.categories.count()  
8

3.  How many documents are in the "orders" collection?
>  \> db.orders.count()  
830

4.  How many orders were handled by the person with EmployeeID number 8?
>  \> db.orders.count( {EmployeeID: 8} )  
104

5.  What is the last name of the employee who has the EmployeeID number 1?
>  \> db.employees.find( { EmployeeID: 1 }, { \_id: 0, LastName: 1 } )  
{ "LastName" : "Davolio" }

6.  What are the EmployeeID numbers on orders which have an OrderID less than 10300?
>  \> db.orders.distinct( "EmployeeID", { "OrderID": { $lt: 10300 } } )  
[ 5, 4, 3, 9, 1, 8, 6, 2, 7 ]

7.  What are the Company Names of the suppliers?
>  \> db.suppliers.distinct( "CompanyName" )  
[  
	"New Orleans Cajun Delights",  
	"Grandma Kelly's Homestead",  
	"Tokyo Traders",  
	"Cooperativa de Quesos 'Las Cabras'",  
	"Mayumi's",  
	"Pavlova",  
	"Specialty Biscuits",  
	"PB Knäckebröd AB",  
	"Refrescos Americanas LTDA",  
	"Heli Süßwaren GmbH & Co. KG",  
	"Plutzer Lebensmittelgroßmärkte AG",  
	"Nord-Ost-Fisch Handelsgesellschaft mbH",  
	"Exotic Liquids",  
	"Formaggi Fortini s.r.l.",  
	"Norske Meierier",  
	"Bigfoot Breweries",  
	"Aux joyeux ecclésiastiques",  
	"Svensk Sjöföda AB",  
	"Leka Trading",  
	"Lyngbysild",  
	"Zaanse Snoepfabriek",  
	"Karkki Oy",  
	"Pasta Buttini s.r.l.",  
	"Escargots Nouveaux",  
	"Gai pâturage",  
	"G'day",  
	"Ma Maison",  
	"New England Seafood Cannery",  
	"Forêts d'érables"  
]  

8.  How many suppliers are there?
>  \> db.suppliers.count()  
29

9.  What is the supplier ID and phone number for the supplier in Boston, Mass.? Be sure NOT to include the ID of the document...
>  \> db.suppliers.find( { City: "Boston" }, { \_id: 0, SupplierID: 1, Phone: 1 } )  
{ "SupplierID" : 19, "Phone" : "(617) 555-3267" }

10.  What employee is responsible for the largest number of orders, and for how many orders is that employee responsible?
>  TODO

11.  How many territories have the RegionID value of "2"?  What are their territory descriptions? Be sure NOT to include the ID of the document, and ONLY show the territory descriptions.
>  \> db.territories.count( { RegionID: 2 } )  
15  
\> db.territories.find( { RegionID: 2 }, { \_id: 0, TerritoryDescription: 1 } )  
{ "TerritoryDescription" : "Chicago" }  
{ "TerritoryDescription" : "Denver" }  
{ "TerritoryDescription" : "HoffmanEstates" }  
{ "TerritoryDescription" : "ColoradoSprings" }  
{ "TerritoryDescription" : "Phoenix" }  
{ "TerritoryDescription" : "Scottsdale" }  
{ "TerritoryDescription" : "SantaMonica" }  
{ "TerritoryDescription" : "MenloPark" }  
{ "TerritoryDescription" : "Campbell" }  
{ "TerritoryDescription" : "SanFrancisco" }  
{ "TerritoryDescription" : "SantaClara" }  
{ "TerritoryDescription" : "SantaCruz" }  
{ "TerritoryDescription" : "Redmond" }  
{ "TerritoryDescription" : "Bellevue" }  
{ "TerritoryDescription" : "Seattle" }  

12.  What is the phone number of the shipper with the company name "United Package"? Be sure NOT to include the ID of the document in the output, ONLY the phone number.
>  \> db.shippers.find( { CompanyName: "United Package" }, { \_id: 0, Phone: 1 } )  
{ "Phone" : "(503) 555-3199" }

BONUS:

13.  How many documents are in the "order-details" collection?  How many in the "employee-territories" collection?
>  \> db["order-details"].count()  
2155  
>  \> db["employee-territories"].count()  
49

14.  How many orders were shipped to Albuquerque, NM?  What are the order numbers? Be sure NOT to include the ID of the document in the output, ONLY the Order ID numbers.
>  \> db.orders.count( { ShipCity: "Albuquerque" } )  
18  
\> db.orders.find( { ShipCity: "Albuquerque" }, { \_id: 0, OrderID: 1 } )  
{ "OrderID" : 10262 }  
{ "OrderID" : 10272 }  
{ "OrderID" : 10294 }  
{ "OrderID" : 10314 }  
{ "OrderID" : 10316 }  
{ "OrderID" : 10346 }  
{ "OrderID" : 10401 }  
{ "OrderID" : 10479 }  
{ "OrderID" : 10569 }  
{ "OrderID" : 10564 }  
{ "OrderID" : 10598 }  
{ "OrderID" : 10761 }  
{ "OrderID" : 10820 }  
{ "OrderID" : 10852 }  
{ "OrderID" : 10889 }  
{ "OrderID" : 10988 }  
{ "OrderID" : 11000 }  
{ "OrderID" : 11077 }  


###  Neo4j Database Exercise

Use single queries for these, meaning you may NOT execute one query and then execute a second, third, fourth, ....., n'th query to determine maximums, minimums or counts.

1.  What are the different collections in the Northwind database?
>  TODO

2.  How many documents are in the "categories" label set?
>  \> MATCH (n:Category) RETURN n
8

3.  How many documents are in the "orders" label set?
>  \> MATCH (n:Order) RETURN n
830

4.  How many orders were handled by the person with EmployeeID number 8?
>  \> MATCH (n:Orders) WHERE n.EmployeeID = '8' RETURN n
104

5.  What is the last name of the employee who has the EmployeeID number 1?
>  \> MATCH (n:Employee) WHERE n.employeeID = '1' RETURN n.lastName
"Davolio"

6.  What are the EmployeeID numbers on orders which have an OrderID less than 10300?
>  \> MATCH (n:Orders) WHERE n.OrderID < '10300' RETURN DISTINCT n.EmployeeID
╒══════════════╕
│"n.EmployeeID"│
╞══════════════╡
│"5"           │
├──────────────┤
│"6"           │
├──────────────┤
│"4"           │
├──────────────┤
│"3"           │
├──────────────┤
│"9"           │
├──────────────┤
│"1"           │
├──────────────┤
│"8"           │
├──────────────┤
│"2"           │
├──────────────┤
│"7"           │
└──────────────┘

7.  What are the Company Names of the suppliers?
>  \> MATCH (n:Supplier) RETURN n.companyName
╒════════════════════════════════════════╕
│"n.companyName"                         │
╞════════════════════════════════════════╡
│"Exotic Liquids"                        │
├────────────────────────────────────────┤
│"New Orleans Cajun Delights"            │
├────────────────────────────────────────┤
│"Grandma Kelly's Homestead"             │
├────────────────────────────────────────┤
│"Tokyo Traders"                         │
├────────────────────────────────────────┤
│"Cooperativa de Quesos 'Las Cabras'"    │
├────────────────────────────────────────┤
│"Mayumi's"                              │
├────────────────────────────────────────┤
│"Pavlova"                               │
├────────────────────────────────────────┤
│"Specialty Biscuits"                    │
├────────────────────────────────────────┤
│"PB Knäckebröd AB"                      │
├────────────────────────────────────────┤
│"Refrescos Americanas LTDA"             │
├────────────────────────────────────────┤
│"Heli Süßwaren GmbH & Co. KG"           │
├────────────────────────────────────────┤
│"Plutzer Lebensmittelgroßmärkte AG"     │
├────────────────────────────────────────┤
│"Nord-Ost-Fisch Handelsgesellschaft mbH"│
├────────────────────────────────────────┤
│"Formaggi Fortini s.r.l."               │
├────────────────────────────────────────┤
│"Norske Meierier"                       │
├────────────────────────────────────────┤
│"Bigfoot Breweries"                     │
├────────────────────────────────────────┤
│"Svensk Sjöföda AB"                     │
├────────────────────────────────────────┤
│"Aux joyeux ecclésiastiques"            │
├────────────────────────────────────────┤
│"New England Seafood Cannery"           │
├────────────────────────────────────────┤
│"Leka Trading"                          │
├────────────────────────────────────────┤
│"Lyngbysild"                            │
├────────────────────────────────────────┤
│"Zaanse Snoepfabriek"                   │
├────────────────────────────────────────┤
│"Karkki Oy"                             │
├────────────────────────────────────────┤
│"G'day"                                 │
├────────────────────────────────────────┤
│"Ma Maison"                             │
├────────────────────────────────────────┤
│"Pasta Buttini s.r.l."                  │
├────────────────────────────────────────┤
│"Escargots Nouveaux"                    │
├────────────────────────────────────────┤
│"Gai pâturage"                          │
├────────────────────────────────────────┤
│"Forêts d'érables"                      │
└────────────────────────────────────────┘

8.  How many suppliers are there?
>  \> MATCH (n:Supplier) RETURN n
29

9.  What is the supplier ID and phone number for the supplier in Boston, Mass.?
>  \> MATCH (n:Suppliers) WHERE n.City = 'Boston' AND n.Region = 'MA' RETURN n.SupplierID, n.Phone
╒══════════════╤════════════════╕
│"n.SupplierID"│"n.Phone"       │
╞══════════════╪════════════════╡
│"19"          │"(617) 555-3267"│
└──────────────┴────────────────┘

10.  What employee is responsible for the largest number of orders, and for how many orders is that employee responsible?
>  TODO

11.  How many territories have the RegionID value of "2"?  What are their territory descriptions? You can use two queries. Be sure to ONLY show the territory descriptions for that query.
>  \> MATCH (n:Territory) WHERE n.regionID = '2' RETURN count(n)
15
\> MATCH (n:Territory) WHERE n.regionID = '2' RETURN n.territoryDescription
╒════════════════════════╕
│"n.territoryDescription"│
╞════════════════════════╡
│"HoffmanEstates"        │
├────────────────────────┤
│"Chicago"               │
├────────────────────────┤
│"Denver"                │
├────────────────────────┤
│"ColoradoSprings"       │
├────────────────────────┤
│"Phoenix"               │
├────────────────────────┤
│"Scottsdale"            │
├────────────────────────┤
│"SantaMonica"           │
├────────────────────────┤
│"MenloPark"             │
├────────────────────────┤
│"SanFrancisco"          │
├────────────────────────┤
│"Campbell"              │
├────────────────────────┤
│"SantaClara"            │
├────────────────────────┤
│"SantaCruz"             │
├────────────────────────┤
│"Bellevue"              │
├────────────────────────┤
│"Redmond"               │
├────────────────────────┤
│"Seattle"               │
└────────────────────────┘

12.  What is the phone number of the shipper with the company name "United Package"? Be sure to ONLY include the phone number in the result.
>  TODO

BONUS:

13.  How many relationships are in the "order-details" edges set?  How many in the "employee-territories" edges set?
>  TODO

14.  How many orders were shipped to Albuquerque, NM?  What are the order numbers?
>  TODO
