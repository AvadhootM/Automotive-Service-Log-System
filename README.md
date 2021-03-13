Automotive-Service-Log-System


Background: 

The conservative method of tracking service history of a vehicle is a tedious process which not only consumes time but also other resources such as money and proper allocation of parts and labors. Managing multiple service records of multiple car combined with tracking inventory of required service parts is a difficult task. Automating service log management system will help you to track service records efficiently and forecast the number of service parts that are regularly used. The service centers can now serve its customers productively making this a win-win situation for both parties where they end up saving multiple resources.


Purpose: 

Design and deploy a relational database system for automotive dealerships to store and retrieve data of vehicle, service history, service check-in details and corresponding customer details


Abstract:

Creating and maintaining a centralized database which would be used to store a huge amount of data across service providers and would store Customer data and the services they have purchased. The analysis of this data would help user with a consolidated view of service records and would help with inventory management.


Entity Relationship Diagram


![image](https://user-images.githubusercontent.com/64949763/111036397-fd4af280-83ec-11eb-809e-a2a47e4437c3.png)


Entities
-	Vehicle:
Vehicle entity contains all the information about the vehicle at the service centre. The primary key is ‘Vehicle_ID’; it also contains the foreign key ‘Customer_ID’. This entity has vehicle details like “Vehicle_Type”, “Color”, “Manufacturing_year”, “Price”, “Mileage”, “Vehicle_Model”, “Brand”, “Fuel_Type”. It has a many to one relationship with the customer table, one to one relationship with vehicle warranty and insurance table. One to Many relationships with store location, one to optional one with Delivery table.

-	Customer:
This entity contains all the information about the customer and “Customer_ID” is the primary key. This entity contains “Customer_Name”, “Address”, “DOB”, “Email_ID”, “Phone_Number”. It has one to many relationships with ‘Payment Info’

-	Vehicle Warranty:
This entity contains information like Registration number,Date of Purchase, Warranty Period and Description. ‘Registration No’ is the primary key and ‘VehicleID’ is Foreign key, one to one relationship with the Vehicle table.

-	Service:
It contains the information of the service request by the customer. The Query_ID is the primary key for this entity. Complaint details contain the info about the complaint and the phone number contains the phone number of the customer. Date and time contain the info of the moment the complaint was received. The type of request is recorded in RequestType, VehicleID is the foreign key. It has many to one relationship with Vehicle table.

-	Part Warranty:
This entity contains information like Part_number,Date_of_Purchase, Warranty_Period and Description. ‘Part_No’ is the primary key and ‘Vehicle_ID’ is Foreign key, one to many relationships with the Accessories. Number of years that warranty is valid from the date of purchase, optional one to many with accesories table.

-	Delivery:
It contains delivery details of a vehicle. ’Delivery_ID’ is the primary key of this entity and it contains foreign key ‘Vehicle ID’. This table has. Delivery_Location, Delivery_Date, Delivery_Time and Contact_No of delivery executives. It has optional One to One relationship with the vehicle table.

-	Insurance: 
Insurance entities are made to record the details of the vehicle insurance policies purchased by the customers. A ‘Insurance No.’ is allotted to every new policy purchased by the customer, it is the primary key for the table.  One to One relationship with the Vehicle table and therefore, ‘Vehicle_ID’ is the foreign key for the table. Entity has ‘Insurance_Options’ and ‘Descriptions’ as its attributes to record the information.

-	Payment Info:
Payment_ ID the primary key, Customer_ID is the foreign key, it has the attributes, Amount and Mode_Of_Payment. Has a many to one relationship with the customer table.

-	Assigned Employee:
Employee_ID is the primary key, it has attributes, Employee_Name, Phone_Number, Working_Hours. Query_ID is the foreign key. It has a one to many relationships with the Service table and a one to many relationships with itself indicating one employee manages many employees

-	Accessories
Part_no and Vehicle_ID together are foreign keys, the attributes are, Manufacturer, Description, Price. It has one to many relationships with the Vehicle table and Part Warranty table.
