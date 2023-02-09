# AirBnB_clone
This is the first step in the creation of the AirBnB clone project.
By Tom Luther and Kiswa Seif.
### Contents in Repository
**console.py** - Command line intepreter file
**models/__init__.py** - Creates instance of FileStorage
**models/base_model.py** - Class BaseModel, defines ALL attributes for other classes
**models/amenity.py** - Class Amenity, inherits from BaseModel
**models/city.py** - Class City, inherits from BaseModel
**models/place.py** - Class Place, inherits from BaseModel
**models/review.py** - Class Review, inherits from BaseModel
**models/state.py** - Class State, inherits from BaseModel
**models/user.py** - Class User, inherits from BaseModel
**models/engine/file_storage.py** - Class FileStorage, serializes/deserializes instances to a JSON file
**tests/test_models/test_amenity.py** - Tests Amenity class
**tests/test_models/test_base_model.py** - Tests BaseModel class
**tests/test_models/test_city.py** - Tests City class
**tests/test_models/test_place.py** - Tests Place class
**tests/test_models/test_review.py** - Tests Review class
**tests/test_models/test_state.py** - Tests State class
**tests/test_models/test_user.py** - Tests User class
**test/test_models/test_engine/test_file_storage.py** - Tests file_storage file
### How To Install
-   Clone this repository:  `git clone "https://github.com/TomLutherKE/AirBnB_clone.git"`
-   Access AirBnb directory:  `cd AirBnB_clone`
### Using The Console
-   Run hbnb(interactively):
```python
$ ./console.py
(hbnb) help
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
(hbnb)
(hbnb) quit
$
```
-   Run hbnb(non-interactively):
```python
$ echo "help" | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```
### Console Commands
console.py - the console contains the entry point of the command interpreter. List of commands this console supports:
**quit** - exits console
**create** - Creates a new instance of`BaseModel`, saves it (to the JSON file) and prints the id
**destroy** - Deletes an instance based on the class name and id (save the change into the JSON file).
**show** - Prints the string representation of an instance based on the class name and id.
**all** - Prints all string representation of all instances based or not on the class name.
**update** - Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file).
### Examples
```python
$ ./console.py
(hbnb) show BaseModel
** instance id missing **
(hbnb) show BaseModel Holberton
** no instance found **
(hbnb) create BaseModel
49faff9a-6318-451f-87b6-910505c55907
(hbnb) all BaseModel
["[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}"]
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}
(hbnb) destroy
** class name missing **
(hbnb) update BaseModel 49faff9a-6318-451f-87b6-910505c55907 first_name "Betty"
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'first_name': 'Betty', 'id': '49faff9a-6318-451f-87b6-910505c55907', 'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'updated_at': datetime.datetime(2017, 10, 2, 3, 11, 3, 49401)}
(hbnb) create BaseModel
2dd6ef5c-467c-4f82-9521-a772ea7d84e9
(hbnb) all BaseModel
["[BaseModel] (2dd6ef5c-467c-4f82-9521-a772ea7d84e9) {'id': '2dd6ef5c-467c-4f82-9521-a772ea7d84e9', 'created_at': datetime.datetime(2017, 10, 2, 3, 11, 23, 639717), 'updated_at': datetime.datetime(2017, 10, 2, 3, 11, 23, 639724)}", "[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'first_name': 'Betty', 'id': '49faff9a-6318-451f-87b6-910505c55907', 'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 'updated_at': datetime.datetime(2017, 10, 2, 3, 11, 3, 49401)}"]
(hbnb) destroy BaseModel 49faff9a-6318-451f-87b6-910505c55907
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
** no instance found **
(hbnb)
```
