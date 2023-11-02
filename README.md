# Clean Architecture Code

This project is to help with the Clean Architecture Folder Structure and note for flutter.
this is based on 
https://www.youtube.com/playlist?list=PLjyxas0TsCpnjpzCv3rnsX3LjS9G2K05f

## What is Clean Architecture
This is a powerful solution to build clean apps with independent data layers that multiple teams can work on. This is useful for building app that are 
- #### Readable,
- #### Scalable,
- #### Testable &
- #### Maintainable

## Layers
The clean architecture has 3 main layers which include 
- #### Data layer
- #### Domain Layer
- #### Presentation Layer

and supporting layers include 
- Resources and 
- Shared Libraries layers

### PRESENTATION LAYER
This layer presents the app's content and triggers the events that modify the application state, it includes 3 parts
- #### Pages 
    - These are application pages
- #### State Management 
  - state management files eg bloc, riverpod, getx, provider etc
- #### Widgets 
  -  widgets we built or used on the pages

### DOMAIN LAYER   
 This is the innermost part of the layers and has no dependency on other layers. This is written purely in dart without flutter elements because this is supposed to be only concerned with the business logic of the app and not the implementation details of the app  it also has 3 parts
 - #### Entities
   - These are the different data types and classes used in the various parts of our software or Let's say these are the custom data types that can be returned on API calls or used when making a call to external servers 
 - #### Repositories Interfaces 
    - These are abstract classes or contracts when defining the properties and methods that our app would need in specific features 
 - #### Usecases 
   - These include application-specific business rules. Each event refers to a user interaction with the system. example Sign up, Log in etc. This is a bridge between layers, it is a single call to business logic.

  ### DATA LAYER   
  This is part of the outermost layer responsible for data retrieval. These are responsible for making calls to remote servers using APIs or calls to the local database. It also includes Repository implementations. The data layer also contains 3 parts which include: 
  - #### Repositiories
     - This is the concrete implementation of the repositories interface in the Domain layer. These are responsible for coordinating data from the different data sources
  - #### Data Source 
    - These consist of
    - #### Local Data sources 
      -  cache or persist data on a local drive
    - #### Remote Data sources 
      - Remote Data Sources perform HTTP requests on the APIs
  - #### Models 
    - These are the representation of JSON structured data and allow us to interact with our data sources.

## GO TO THE LIB FOLDER FOR THE FOLDER STRUCTURE
 - #### features Folder 
    This contains all the features of the app, each feature would have 3 folders
     - #### data
       - repository
       - data_sources
       - models
     - #### domain
       - usecases
       - entities
       - repository
     - #### presentation
       - pages
       - getx
       - widgets 
 -  #### config Folder
    This contains the project-related  configurations
    - #### theme
    - #### routes
 -  #### core Folder
    This contains  anything that needs to be shared among multiple features in the project eg
     - #### network
     - #### error
     - #### util
     - #### usecases
  
