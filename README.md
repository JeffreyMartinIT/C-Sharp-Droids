# Demonstrate Inheritance, Abstract Classes, Interfaces, and Polymorphism

## Author
Jeffrey Martin


## Description

The Jawas on Tatooine have recently opened a droid factory and they want to hire you to write a program to hold a list of the available droids, and the price of each droid. The price is based on the type: (protocol, utility, janitor, or astromech), the material used and the options selected by the Jawa creating the list.

The program will keep a list of Droids that are created. This list can be either an array or in the form of one of the C# List classes. The array or list should be of a type that is high enough on the inheritance chain that all droids no matter what type they are can be stored in it. (Think Polymorphism)

A Jawa will be presented with a user interface to add a new Droid, or print the current Droid list. Adding a new Droid will require input from the Jawa to create the new droid. Once all of the needed information is added for the droid, the new droid will be added to the list.

If a Jawa decides to print the list of droids in inventory, the program should loop through all of the droids in the list and print out the information from ToString, and the TotalCost for each droid. This should be accomplished using Polymorphism to reduce the amount of code needed.

All of the prices for the various aspects of a droid are left up to you to determine. If I was doing it though, I would probably have a small set price for each of the following general options, and not get too specific to save time. ie:
1. A price for model(protocol, utility, etc.)
2. A few different materials (Something Made up), each with a differnet price
3. A price for each additional option (One of the various option bools listed below. One price for all will work)
4. A price per quantity option such as: numberOfLanguages, and numberOfShips

The program comes with an Interface IDroid that must be implemented by subclasses. It contains a public method called CalculateTotalCost, and a public Property called TotalCost. CalculateTotalCost returns a void, so it's job is to access the properties of the droid and literally calculate the total cost.

The program has a base abstract class called Droid with the following variables, properties, constructors, methods, etc that implements the IDroid interface.

Droid:
* Variables: material (string), model (string), color (string), baseCost (decimal), totalCost (decimal)
* Constructors: 3 parameter constructor (string, string, string)
* Property: TotalCost to return the cost of the droid (Required by the interface)
* Methods:
	* ToString: return a formatted string containing the variables
	* CalculateBaseCost: Determines the baseCost based on material and type.
	* CalculateTotalCost: assigns baseCost to totalCost (Required by the interface)

There are two derived classes from the abstract class Droid with appropriate variables, methods and properties.

Protocol:
* Variables: numberLanguages (int)
* Constant: costPerLanguage
* Constructors: 4 parameter constructor (string, string, string, int)
	* Uses the base class (Droid) constructor
* Methods:
	* ToString: return a formatted string containing the variables
	* CalculateTotalCost: Calculate the totalCost based on the number of languages and adds it to the base totalCost

Utility:
* Variables: toolbox (bool), computerConnection (bool), arm (bool)
* Constructors: 6 parameter constructor (string, string, string, bool, bool, bool)
	* Uses the base class (Droid) constructor
* Methods:
	* ToString: return a formatted string containing the variables
	* CalculateTotalCost: Calculates totalCost by calculating the cost of each selected option and add it to the base totalCost.

There are two more derived classes from the class Utility with appropriate variables, methods and properties.

Janitor:
* Variables: trashCompactor (bool), vacuum (bool)
* Constructors: 8 parameter constructor (string, string, string, bool, bool, bool, bool, bool)
	* Uses the base class (Utility) constructor
* Methods:
	* ToString: return a formatted string containing the variables
	* CalculateTotalCost: Calculate totalCost by calculating the cost of each selected option and adds it to the base totalCost

Astromech:
* Variables: fireExtinquisher (bool), numberShips (int)
* Constant: costPerShip
* Constructors: 8 parameter constructor (string, string, string, bool, bool, bool, bool, int)
	* Uses the base class (Utility) constructor
* Methods:
	* ToString: return a formatted string containing the variables
	* CalculateTotalCost: Calculate totalCost by calculating the cost of each selected option and the cost based on the number of ships and adds both to the base CalculateTotalCost

A UI class that will handle getting all of the necessary information from the Jawa, and display the feedback to the Jawa.



## Outside Resources Used
http://www.c-sharpcorner.com/code/448/code-to-auto-maximize-console-application-according-to-screen-width-in-c-sharp.aspx

## Known Problems, Issues, And/Or Errors in the Program
None