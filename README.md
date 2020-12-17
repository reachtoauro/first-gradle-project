## First Gradle Java Project
build a simple Java project using Gradle

# Install in Mac
`brew install gradle`

# Gradle commands
- `gradle` : version including other information
- `gradle tasks` : list of available tasks
- `gradle build` : task compiles, tests, and assembles the code into a JAR file
- `gradle wrapper --gradle-version 6.0.1` : gradle wrapper doesn't rely on your local gradle
- `./gradlew build` : use the wrapper script to perform the build task(for gradle wrapper build project only)
- `./gradlew run` : build and run (for gradle wrapper build project only)

# build.gradle plugins
- `apply plugin: 'java'` -  added in the build configuration
- `apply plugin: 'application'` - make the JAR runnable
- `mainClassName` - define the starter class

# build.gradle blocks
- `repositories` : indicates that the build should resolve its dependencies from
- `dependencies` : declare dependencies, from right to left version library, in the joda-time group
    - compile time dependency : should be available during compile-time
    - `implementation` : dependencies for compiling the project code, but that will be provided at runtime by a container running the code
    - `testImplementation` : dependencies used for compiling and running tests, but not required for building or running the project’s runtime code.
- `jar` : specify the name for our JAR artifact, specifies how the JAR file will be named e.g, `<archiveBaseName>-<archiveVersion>.jar`
    - archiveBaseName
    - archiveVersion


# Gradle Wrapper
Gradle Wrapper is the preferred way of starting a Gradle build. he Gradle Wrapper files are designed to be committed to source control so that anyone can build the project without having to first install and configure a specific version of Gradle.
    - consists of a batch script for Windows and a shell script for OS X and Linux
    - scripts allow you to run a Gradle build without requiring that Gradle be installed on your system
    - with the command : `gradle wrapper --gradle-version 6.0.1` 
    - above mentioned two scripts are in the root of the folder
    - the wrapper jar and properties files have been added to a new gradle/wrapper folder

# Run
- `jar tvf build/libs/gs-gradle-0.1.0.jar` : take a look inside the generated jar file contents
- `./gradlew run` : running a runnable JAR

# More to explore
 - building WAR use `war` plugin - https://docs.gradle.org/current/userguide/war_plugin.html
 - building `spring boot` application use `spring-boot-gradle-plugin` - https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using-boot-gradle

