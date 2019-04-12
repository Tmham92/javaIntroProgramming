# Processing input from the command line & applying inheritance

## Learning outcomes

* processing command-line arguments
* being able to create and implement a simple OO design

## Assignment details

For this assignment, you will need to process some input from the command-line and, 
according to the info in the command-line you will need to instantiate the correct subclass to the supertype: Animal.
Also, you will need to override some methods to reflect the properties and habits of the subtype.

In this scenario, there is a superclass, Animal, that defines some basic ... animal behaviour. 
As you may well know, all animals are able to generate sound and are able to move.  
Of course, they tend to do this in vastly differing ways.

Another aspect that is quite universal for animals is that they tend to move slower when they are nearing seniority.  
The mathematical equation that has been determined (after years and years of expensive research)
 to approximate animal moving speed relative to the species' maximum speed is:  

```
speed = max_speed * (0.5 + (0.5 * ((max_age - age) / max_age)))
```

Of course, you will have to do some checking here: ages can never exceed the species maximum speed and age can never be negative.  

These are the animal species you will have to support in your application:


Species       | Maximum speed  | Maximum age  | Moving type
------------- | -------------- | ------------ | ------------
Mouse         | 21             | 13           | scurry
Horse         | 88             | 62           | gallop
Elephant      | 40             | 86           | thunder
Tortoise      | 0.3            | 190          | crawl

Of course, speeds are in km and ages in years!  

Given these animal species, implement the subclasses in the correct way, 
so that all objects behave correctly in this simulation system.

The tool should be given arguments at the command-line indicating which species to create and what age it is.  
Multiple animals should be accepted by the application.  
The application should then let the animals in question demonstrate their core business.  

Here is some example command-line usage and output

```
user_x@bin200$ java AnimalSimulator Horse 21 Elephant 2
A Horse of age 21 moving in gallop at 73.1 km/h
An Elephant of age 2 moving in thunder at 39.5 km/h
```

Two details should be pointed out here: 
1. When the name of the species starts with a consonant, the first word is simply "A", with vowels it is "An"
2. The animal speed is rounded to one decimal, and the decimal is a dot, not a comma!

Just to remind you, when user input is processed, you should ALWAYS check this and give nice error messages.

This is expected output when an illegal data is provided, or when help is requested:

```
user_x@bin200$ java AnimalSimulator Tortoise 199
Error: maximum age of Tortoise is 190 years. Please give new values
user_x@bin200$ java AnimalSimulator "Porpoise 58"
Error: animal species Portoise is not known. run with single parameter "help" to get a listing of available species. Please give new values
user_x@bin200$ java AnimalSimulator help
Usage: java AnimalSimulator <Species age Species age ...>
Supported species (in alphabetical order):
1: Elephant
2: Horse
3: Mouse
4: Tortoise
```
