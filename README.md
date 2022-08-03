```

░█████╗░██╗██████╗░██████╗░███╗░░██╗██████╗░  ░█████╗░██╗░░░░░░█████╗░███╗░░██╗███████╗
██╔══██╗██║██╔══██╗██╔══██╗████╗░██║██╔══██╗  ██╔══██╗██║░░░░░██╔══██╗████╗░██║██╔════╝
███████║██║██████╔╝██████╦╝██╔██╗██║██████╦╝  ██║░░╚═╝██║░░░░░██║░░██║██╔██╗██║█████╗░░
██╔══██║██║██╔══██╗██╔══██╗██║╚████║██╔══██╗  ██║░░██╗██║░░░░░██║░░██║██║╚████║██╔══╝░░
██║░░██║██║██║░░██║██████╦╝██║░╚███║██████╦╝  ╚█████╔╝███████╗╚█████╔╝██║░╚███║███████╗
╚═╝░░╚═╝╚═╝╚═╝░░╚═╝╚═════╝░╚═╝░░╚══╝╚═════╝░  ░╚════╝░╚══════╝░╚════╝░╚═╝░░╚══╝╚══════╝
```

![AirBnB](assets/hbnb_logo.png)

## DESCRIPTION

**AirBnB** is a *complete web application*, integrating database storage, a back-end API, and front-end interface.

This is part 1 of our AirBnb Clone project. The purpose of this project is to make a command interpreter that manages our AirBnb objects.

#### Data Diagram

![data_diagram](assets/data_diagram.jpg)

## CONCEPTS LEARNT

-    How to create a Python package
-    How to create a command interpreter in Python using the `cmd` module
-    What is Unit testing and how to implement it in a large project
-    How to serialize and deserialize a Class
-    How to write and read a JSON file
-    How to manage `datetime`
-    What is an `UUID`
-    What is `*args` and how to use it
-    What is `**kwargs` and how to use it
-    How to handle named arguments in a function


## SYNOPSIS

#### Starting the Commandline Interpreter
The Commandline Interpreter can be started by executing the command `./console.py`. The `console` can `create`, `destroy`, and `update` objects. Type `help` within the console to get a list of command options and its function.

**Example:**
```bash
dare-hp@ubuntu:~$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  create  help  quit

Undocumented commands:
======================
all  destroy  show  update

(hbnb) help quit
Quit command to exit the program
(hbnb) quit
dare-hp@ubuntu:~$
```
### OBJECTS IMPLEMENTED
This repository contains the following files:

| Folder | File | Description |
| :--- | :--- | :--- |
| tests |  | Contains test files for AirBnb Clone |
|  | console.py | Command line Interpreter for managing AirBnB objects |
| models | base_model.py | Defines all common attributes/methods for other classes |
| models | amenity.py | Creates class `amenity` |
| models | city.py | Creates class `city` |
| models | place.py | Creates class `place` |
| models | review.py | Creates class `review` |
| models | state.py | Creates class `state` |
| models | user.py | Creates class `user` |
| models/engine/ | file_storage.py | Serializes instances to a JSON file and deserializes JSON file to instances |

Usage
The console works both in interactive mode and non-interactive mode, much like a Unix shell. It prints a prompt (hbnb) and waits for the user for input.

Command	Example
Run the console	./console.py
Quit the console	(hbnb) quit
Display the help for a command	(hbnb) help <command>
Create an object (prints its id)	(hbnb) create <class>
Show an object	(hbnb) show <class> <id> or (hbnb) <class>.show(<id>)
Destroy an object	(hbnb) destroy <class> <id> or (hbnb) <class>.destroy(<id>)
Show all objects, or all instances of a class	(hbnb) all or (hbnb) all <class>
Update an attribute of an object	(hbnb) update <class> <id> <attribute name> "<attribute value>" or (hbnb) <class>.update(<id>, <attribute name>, "<attribute value>")
Non-interactive mode example

$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
Models
The folder models contains all the classes used in this project.

File	Description	Attributes
base_model.py	BaseModel class for all the other classes	id, created_at, updated_at
user.py	User class for future user information	email, password, first_name, last_name
amenity.py	Amenity class for future amenity information	name
city.py	City class for future location information	state_id, name
state.py	State class for future location information	name
place.py	Place class for future accomodation information	city_id, user_id, name, description, number_rooms, number_bathrooms, max_guest, price_by_night, latitude, longitude, amenity_ids
review.py	Review class for future user/host review information	place_id, user_id, text
File storage
The folder engine manages the serialization and deserialization of all the data, following a JSON format.

A FileStorage class is defined in file_storage.py with methods to follow this flow: <object> -> to_dict() -> <dictionary> -> JSON dump -> <json string> -> FILE -> <json string> -> JSON load -> <dictionary> -> <object>

The init.py file contains the instantiation of the FileStorage class called storage, followed by a call to the method reload() on that instance. This allows the storage to be reloaded automatically at initialization, which recovers the serialized data.

Tests
All the code is tested with the unittest module. The test for the classes are in the test_models folder.

Authors
John Damilare   - dare.john18@gmail.com
Adewale Aderoju - xxxxxxxxx@gmail.com

