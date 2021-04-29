# cs3200
Aric Zhu's final project for CS3200 Sec 04. Cheers!

1.	Title
Cocktail Recipe & Experience Tracker

2.	Team name
n/a

3.	Member
Aric Zhu Sec 04

4. Description
This database allows users to track cocktails: it includes tables for recipes, ingredients, and ingredient quantities required for each cocktail to facilitate making it. 
Furthermore, each ingredient is classified via a portable enumeration to clarify potentially unknown items. 
The database acknowledges that a cocktail can have multiple recipes. 
Users can enter their experiences of whether they have tried a specific cocktail recipe and record recipe ratings.

5.	UML Diagram
Included in repository.

6.	User data model
User
The User class keeps track of each user's basic information and information used to create their account. 
firstName: string - user first name
lastName: string; not required - user last name
username: string - username
password: string - account password
email: string - email used to register account
dateOfBirth: date - user date of birth
created: datetime - datetime account was created
updated: datetime - datetime account was updated

7.	Domain object data models

Cocktails
The Cocktails class records the name of a cocktail and if it is alcoholic.
name: string - cocktail name
alcoholic: Boolean - True if cocktail includes alcohol, False otherwise

Ingredients
The Ingredients class records all ingredients used in a cocktail and categorizes them via portable enumeration.
name: string; unique - ingredient name, must be unique
category: string - ingredient classification, uses Categories class to enumerate

Recipes
This records the instructions for making a cocktail and when the recipe was entered and updated into the database.
guide: string - instructions on how to create the cocktail
source: string - original author or website 
created: datetime - datetime cocktail recipe entered
updated: datetime - datetime cocktail recipe was altered

8.	User to Domain object relationship
Users to Recipes is a many to many relationship. A user can taste many recipes, and a recipe can be made by many users. 
This is reified via an Experience class. User - Experience is a one to many relationship and Recipe - Experience is many to one.
This allows users to individually rate each cocktail recipe.
tasted: Boolean - True if user has tasted the recipe, False otherwise
rating: int; not required - user-given rating for a recipe
created: datetime - when experience was created
updated: datetime - when experience was updated

9. 	Domain object to domain object relationship
Recipes - Cocktails is a many - one relationship. A recipe makes one cocktail, but a cocktail can have multiple recipes.
Recipes - Ingredients is many - many. Recipes use multiple ingredients and ingredients are used in many recipes.
This is reified via a Quantity class. Quantity tracks how much each ingredient is used in a recipe.
quantity: dec - amount of ingredient used
unit: str - measurement tool

10.	Portable Enumeration
Each ingredient is classified by drink mix type: beer, fruit, herb, juice, liqueur, liquor, soda, sweetener, temperature, vegetable, wine
This is implemented by the Categories class. Ingredients - Categories is a many - one (enumeration) relationship.
