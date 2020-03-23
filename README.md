# Tutorial_Demo

### Background

Continuous integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project. The practice requires developers to integrate code often, at least once a day if possible to allow the detection of problems early. Today there are many automatic tools to assist the process and make sure that code is correct before integration. 

In this tutorial we will look at TeamCity which is a build management and continuous integration server from JetBrains and how to set it up with a gradle project. We will look at installation and setup of Teamcity step by step for Linux/Mac.


## Getting Started

Follow theses instruction to set up Teamcity with a gradle project. This setup will let you run TeamCity with a gradle project and can be modified for other framework as well.

### Prerequisite

Download TeamCity from the [website](https://www.jetbrains.com/teamcity/download/#section=section-get). Extract the compressed folder, either by right clicking it and selecting your tool of choice or by using the command ```tar xfz TeamCity<version number>.tar.gz```.

Make sure you java 8 installed (for example, use SDKman) and check your Java version with ```java -version```, also make sure the patch is correct ```echo $JAVA_HOME```.

### Setup
To start the server and default agent, navigate to the bin folder inside the TeamCity folder and run the command ``` ./runAll.sh start``` or ```sh runAll.sh start```. To stop the server, use ```./runAll.sh stop``` or ``` sh runAll.sh stop```.

Open TeamCity by connecting via the browser with http://localhost:8111/.
If another service uses the port, change the port in the XML node in <TeamCity directory>/conf/server.xml
  
Optionally, you can install the Gradle Build Scan Integration plugin. This can be done from the JetBrains plugins repository in TeamCity or by downloading the zip manually and adding it in the Web UI or locally in the TeamCity data directory.

### Configuration

In the TeamCity client, click Administration --> Projects --> Create project.


## Quickguide

*Download: [TeamCity](https://www.jetbrains.com/teamcity/download/#section=section-get)

*Navigate to bin folder and run ./runAll.sh start``` or ```sh runAll.sh start```.

*http://localhost:8111/






