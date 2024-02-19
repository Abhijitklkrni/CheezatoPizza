
Use Case diagram

@startuml left to right direction

actor Admin actor Customer

rectangle Cheezato_Pizza{

usecase "Pay Online" as PayOnline
usecase "Pay Cash" as PayCash
usecase "Login" as Login

Admin --> (Add a product)
Admin --> (Delete a product)
Admin --> (Update order details)
Admin --> Login

Customer --> (Pay)
Customer --> (Check Location Servicability)
Customer --> (Request Order delivery)
Customer --> Login

PayOnline .> (Pay) : extends
PayCash .> (Pay) : extends
} @enduml

3A9303B9-CA38-42FF-A714-FA2BEBE990DE

CLASS DIAGRAM UML CODE - https://www.plantuml.com/plantuml/duml/PL7BQiCm4BplL-XSd2zm2KaJkGGSnyXj82UZMaigQij53nTY-k_To34XzAAHPcTtsD7AUMbzw5feMkaS4qX4iDBu4HQiybQRCpEomvIUgWyVBJ8hFR7flQxGDLP_UzsRAxjkl1wmyj87nro458ZFjVFFcw2TDhXapNHniKCfY-Gk8qPgZoQmZevqxXGuQFnPCXkHHBy0LEyU_4ROl0l1YxVyL5TS77V5QmAR_53nRPqTHBtb-Ux8nIbXK7AnNnSavQIT977cFGBsj7ZSvcPuss64KbykCe5IEa-G4R2ixrK2rQVymWHUS40hp-Z-pvs7m1Jy7C48L-aAZQ8_-GC0

@startuml class Restaurant{

int restaurantId;

String name;

double rating;

String description;

ActiveStatus status;

List cuisines;

List contacts;

Address address;

Menu menu;

List reviews; }

enum ActiveStatus{ CURRENTLY_SERVING, CLOSED_FOR_DELIVERY, PERMANENTELY_CLOSED; }

Restaurant *-- ActiveStatus

enum Cuisine{ Pizza, Pasta, Fast Food, Shake, Beverages }

Restaurant *-- Cuisine

class Contact{

String name;
String phoneNumber; }
Restaurant o-- Contact

class Address{

String addressDesc;
String city;
String state; }
Restaurant o-- Address

class Menu{ List foodItems;

}

Restaurant o-- Menu

class FoodItems{ String restaurantId; String itemId; List itemTags;

}

class Item{ long itemId; String itemname; String itemDesc; double price; double rating;

}

Enum ItemTags{ Chefs Special, Spicy, very spicy, Veg, Non veg }

class Review{ String comment; long upVote; long downVote; }

@enduml