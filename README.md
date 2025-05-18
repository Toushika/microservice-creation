# MicroService-Creation Guide

This guide helps you manually set up a Spring Boot-based microservice with a clean structure and modular architecture. Follow the steps below carefully.

---

## 🛠️ Step-by-Step Setup

### 1. Create Root Project

* Create a new **Spring Boot project** using your preferred IDE (e.g., IntelliJ or Spring Initializr).
* **Do not select any dependencies** during the setup.

### 2. Clean Up Project Structure

After creating the project, **delete the following files and folders** to clean the structure:

```
.idea/
.gradle/
build/
src/
gradlew
gradlew.bat
.git-attributes
HELP.md
```

**Keep only the following files:**

```
gradle/
.gitignore
build.gradle
settings.gradle
```

look the project structure in master branch

### 3. Update `build.gradle` (Root Project)

* Open the `build.gradle` of your root project.
* Update it as per your organization’s or team’s standard (refer to the `master` branch `build.gradle` if applicable).

### 4. Create a New Module

* In the same project, right-click and select:

  ```
  New > Module > Spring Boot
  ```
* Use the **same Java version** (e.g., Java 21) as the root project.

### 5. Add Dependencies to the Module

Select the following dependencies for your new module:

* **Lombok**
* **Spring Web**
* **Spring Boot Actuator**

### 6. Adjust Module in Gradle

* From the **Gradle tab** (on the left side of the IDE), you may see the new module listed separately.
* This indicates the module is not yet linked to the root project.
* So delete rthe module . We will adjust it later.

### 7. Clean Up the Module Folder

Inside the new module directory:

* Keep only:

  ```
  build.gradle
  src/
  ```
* Inside `src/main/resources/`:

  * Delete `static/` and `templates/`
  * **Keep only** `application.properties`

### 8. Update Module's `build.gradle`

* Edit the module's `build.gradle` to define its dependencies and plugin usage.
  look featue/moduleCreation branch data-management folder's build.gradle

  https://github.com/Toushika/microservice-creation/blob/feature/moduleCreation/data-management/build.gradle


### 9. Include the Module in `settings.gradle`

At the root level, open `settings.gradle` and include the module:

https://github.com/Toushika/microservice-creation/blob/feature/moduleCreation/settings.gradle

```groovy
include 'your-module-name'
```

Replace `'your-module-name'` with the actual name of your module folder.

---

## ✅ You're Done!

Your project is now set up as a clean and modular Spring Boot microservice. You can start implementing your business logic.

---
