# Implementing Restful Web Services Using Java and MySQL 
Part of my "Network Oriented Information Systems" course in university was to implement a network oriented information system using resful web services. 
The objective was to do that in the Eclipse IDE for Java developers and use MySQL as our database.

### SYSTEM TOPIC
A pastry shop, named _**Fresh Tart**_, will be the implemented as such:
* an **unregistered user** is able to access a welcome page, the menu and an about us page
* a **registered user** is able to access the aforementioned, as well as an account and an order page, both with their relative options
* an **administrator** is able to access the administrator menu and has the ability to view the registered users and edit the items sold in the shop

### SYSTEM IMPLEMENTATION
Architecture-wise, the REST architecture style was implemented (the RESTful type more precisely); namely, architecture based on the client-server communication (exchange of representations of resources) via a standardized interface and protocol (the stateless HTTP protocol). 

In a RESTful web service:
* the resources and services are identified by Uniform Resource Identifiers (URIs), which are in turn identified by the @Path annotations (*)
* the resources are manipulated by a standard set of CRUD operations; PUT, GET POST, DELETE. The GET operation was vastly used in this project, as it lets us retrieve the current state of a resource
* the contents of a resource can be viewed in different formats; such as plain text, HTML, XML, JSON, JPEG, etc
* even if the interaction between a client and a server is stateless, there are ways in which we can have stateful interactions, such as cookies/sessions and hidden fields

(*)The **@Path** annotation identifies the URI path template to which the resource responds and is specified at the class or method level of a resource. In our project case, a general path is declared in the Java classes responsible for a set of similar web services and a more specific path is specified before each method in those classes.

URI path templates are URIs with variables embedded in their syntax. These variables are “collected” when a service is running in order for a resource to respond to a request based on the substituted URI. Their syntax is as follows:
```java
@Path("BakeryOrders")
@Path("/AddToOrder/{email}/{item}/{quantity}/{orderID}")
```
Where the **BakeryOrders** is the general path of the web service, **AddToOrder** is the unique part of the web service and **email**, **item**, **quantity**, and **orderID** are the parameters given to the web service.

### WEB SERVICES
The following web services were implemented:
1. Register (general)
2. Login (general)
3. Update Username (user)
4. Update E-mail (user)
5. Update Password (user)
6. Delete Account (user)
7. Make an Order
8. Update Order - Add Item to Order
9. Update Order - Remove Item from Order
10. Cancel Order
11. View Order History
12. See Menu
13. Sort Menu by Price
14. See Details of a Product
15. Search
16. Rate Shop
17. Show Ratings
18. Insert Item in Menu
19. Change item Name
20. Change Item Description
21. Change Item Pride
22. Delete Item from Menu
23. Sort Users by Username & E-mail
24. Restock
