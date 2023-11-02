# Clean Architecture Code

This project is to Help with the Clean Architecuture Folder Structure and note for flutter.
this is based on 
https://www.youtube.com/playlist?list=PLjyxas0TsCpnjpzCv3rnsX3LjS9G2K05f

## What is Clean Arcitecture
This is a a powerful solution to build clean apps with independent data layers that multiple teams can work on. This is useful to build app that are 
- #### Readable,
- #### Scalable,
- #### Testable &
- #### Maintanable

## Layers
The clean architecture has 3 main layers which include 
- #### Data layer
- #### Domain Layer
- #### Presentation Layer

and supporting layers include 
- Resouces and 
- Shared Libraries layers

### PRESENTATION LAYER
This layer presents the app's content and triggers the events that modifies the application state, it includes 3 parts
- #### Pages 
    - These are application pages
- #### State Management 
  - state management files eg bloc, riverpod, getx, provider etc
-  #### Widgets 
  -  widgets we built or used on the pages

  ### DOMIAN LAYER   
 This is the inner most part of the layers and have no dependency on other layers. This is written purely in dart without flutter elements because this is supposed to be only concerned with business logic of the app and not the implementaion details of the app  it also has 3 parts
 - #### Entities
   - These are the different data types and classes used in the various parts of our software or Lets say these are the custom data types that can be returned on API call or used when making a call to external servers 
 - #### Repositories Interfaces 
  - These are abstract classes or contracts when define the properties and methods that out app would need in specific features 
 - #### Usecases 
  - These include application specific business rules. Each event refers to a user interaction with the system. example Sign up, Log in etc. This is a bridge between layers, it is a sigle call to business logic.

  ### DATA LAYER   
  This is part of the outter most layer wich is responsible for data retrieval. These are responsible for making call to remote servers using APIs or calls to local data base. It also include Repository implementaions. Data layer also includes 3 parts which includes: 
  - #### Repositiories
     - This is the concrete implementation of the repositories interface in the Domain layer. These are responsible to coordinate data from the different data sources
  - #### Data Source 
    - These consist of
    - #### Local Data sources 
      -  cache or persist data on local drive
    - #### Remote Data sources 
      - Remote Data Sources preform http request on the APIs
  - #### Models 
    - These are the repersentation of JSON structured data and allows us to interact with our data sources.

## GO TO THE LIB FOLDER FOR THE FOLDER STRUCTURE
 - #### features Folder 
    This contains all the features of the app, each feature would have have 3 folders
     - #### data
       - repository
       - data_sources
       - models
     - #### domain
       - usecases
       - entities
       - repository
     - #### presentaion
       - pages
       - getx
       - widgets 
 -  #### config Folder
    This contains the project related  configurations
    - #### theme
    - #### routes
 -  #### core Folder
    This contains  anything that need sto be shared among multiple feature in the project eg
     - #### network
     - #### error
     - #### util
     - #### usecases
  