## Pycon Canada 2018 (Toronto) - Nov 11


### Schedule

- 10:00:
  - Keynote #1: Froilan Iriizarry

- 11:00:
  - Terrace (3rd floor) - You don't need that

- 11:40:
  - Terrace (3rd floor) - [Intake](https://github.com/ContinuumIO/intake) - taking the pain out of data access

- 12:20:
  - Ballroom (2nd floor) -  How to approach scaling Python Web Apps

#### 12:20 LUNCH

- 13:45:
  - Keynote #2: Holden Karau

- 14:45:
  - Ballroom (2nd floor) - Detecting Supernovas

- 15:00:
  - Terrace (3rd floor) - What a bug can teach you about Python

- 15:15:
  - St. Patrick (3rd floor) - The adventure of a Python Script

- 15:30:
  - Ballroom (2nd Floor) -  Flying Python

#### 16:00 BREAK

- 16:20:
  - Terrace (3rd Floor) - BDD -> Behavior Driven Development in Python

- 16:55:
  - St.Davis (3rd floor) -  Building your own crypto exchange in async Python

- 17:30:
  - Ballroom (2nd floor) - Building and scaling Deep Learning Services

#### 18:05 - DONE


## Notes
-----------------------------------------------------------------------------------------------------------------
### Keynote #1 - Froilan Iriizarry. [@skfroi](https://twitter.com/skfroi)
-----------------------------------------------------------------------------------------------------------------

Keep it low tech when you build apps for natural disaster events etc.


-----------------------------------------------------------------------------------------------------------------
### TALK 1: You don't need that - Design Patterns and Python. [@chrisjrn](https://twitter.com/chrisjrn)
-----------------------------------------------------------------------------------------------------------------
> Judge language by its features
#### Design Patterns (Pythonically):
  - Singleton - class can only be constructed once
    - Namespacing - all related data into the same class (Singleton)
    - Pass functionality to other functions
    - >make it a Module
    - in python everything is a variable

  - Dependency injection
    - provide dependencies to classses as you construct them
    - mocks

  - Threads -> asyncio

  - Iterators -> Generators
  - Visitor - perform common operation on a collection
    - Acceptor -> collections, data to process
    - Visitor -> operations to perform on each item in the collection ^^
    - >generators separate the structure from operations you wanna do

  - Bonus slides
    - Factory - instance if an object that fulfills certain interface
        
-----------------------------------------------------------------------------------------------------------------
### TALK 2: [Intake](https://github.com/ContinuumIO/intake) - taking the pain out of data access
-----------------------------------------------------------------------------------------------------------------
```
# install intake
# conda install -c intake intake

import intake
cat = intake.open_catalog('afile.yaml')
df = cat.useful()
```

-----------------------------------------------------------------------------------------------------------------
### TALK 3: How to approach scaling Python Web Apps
-----------------------------------------------------------------------------------------------------------------





-----------------------------------------------------------------------------------------------------------------
### TALK 4: Keynote #2 - Holden Karau
-----------------------------------------------------------------------------------------------------------------





-----------------------------------------------------------------------------------------------------------------
### TALK 5: Detecting Supernovas
-----------------------------------------------------------------------------------------------------------------



-----------------------------------------------------------------------------------------------------------------
### TALK 6: What a bug can teach you about Python
-----------------------------------------------------------------------------------------------------------------



-----------------------------------------------------------------------------------------------------------------
### TALK 7: The adventure of a Python Script
-----------------------------------------------------------------------------------------------------------------




-----------------------------------------------------------------------------------------------------------------
### TALK 8: Flying Python...
-----------------------------------------------------------------------------------------------------------------
