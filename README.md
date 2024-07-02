# Clean Architecture

## Overview

### Presentation/UI
 1. This layer is dealing with handling with UI part.
 2. It contains activity,Fragment,ViewModel and imports with the android packages.

### Domain
 1. This layer dealing with Bussiness logic part.
 2. It contains use cases,repository interfaces.

### Data
 1. This layer deal with all data related part like fetch,store etc.
 2. It contain repository implementation from the case.

## Main Idea
**Inner layer shouldn't depend on outer layer**.That means the repository should have no dependecy on use case, and similaryly the use cases should not depend on the presentation layer(viewmodel).

**Presentation/UI:** This layer purely deals with UI and views system of the Android and it's state handling.

**Domain Layer:** 
  1. The Domain must remain independent of all other layers.
  2. On the other hand, a use case have another use case as it's dependency, allowing the delegation of resposibilities
  3. to the dependent use case, but this can lead to circular dependency in large projects which we need to keep watch on.
  4. Do not hold any state.
  5. It calls a method of the repository to fetch data without knowing how and from where it comes.
  6. No threading details on the Domain layer.

**Data Layer:**
  1. To ensure flexibility in replacing the data layer library, such as Retrofit, with another library without affecting the domain and UI layers,
     the data layer should solely consist of the API and a data source for memory.
  2. It should only depend on `API`, `datasource`.
     
  
### Visual Representation
<img width="1792" alt="app_architecture" src="https://github.com/DevP-ai/CleanArchitecture/assets/107491760/56643b8d-de42-4eaf-841c-e5736f182e9d">

   
    
