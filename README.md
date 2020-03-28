# Tutorial_Demo

### Background

Continuous integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project. The practice requires developers to integrate code often, at least once a day if possible to allow the detection of problems early. Today there are many automatic tools to assist the process and make sure that code is correct before integration. 

In this tutorial we will look at TeamCity which is a build management and continuous integration server from JetBrains and how to set it up with a gradle project in Java. We will look at installation and setup of Teamcity step by step for Linux/Mac. Feel free to use this [repo](https://github.com/Kappenn/Tutorial_Demo) for this tutorial and use it as a skleton for your future project. The Repo is written in Java and set up with Gradle.


## Getting Started

Follow theses instruction to set up TeamCity with a gradle project. This setup will let you run TeamCity with a gradle project and can be modified for other framework as well.

### Prerequisite

Download TeamCity from the [website](https://www.jetbrains.com/teamcity/download/#section=section-get). Extract the compressed folder, either by right clicking it and selecting your tool of choice or by using the command ```tar xfz TeamCity<version number>.tar.gz```.

Make sure you java 8 installed (for example, use SDKman) and check your Java version with ```java -version```, also make sure the patch is correct ```echo $JAVA_HOME```.

### Setup
To start the server and default agent, navigate to the bin folder inside the TeamCity folder and run the command ``` ./runAll.sh start``` or ```sh runAll.sh start```. To stop the server, use ```./runAll.sh stop``` or ``` sh runAll.sh stop```.

Open TeamCity by connecting via the browser with http://localhost:8111/.
If another service uses the port, change the port in the XML node in <TeamCity directory>/conf/server.xml
  
Optionally, you can install the Gradle Build Scan Integration plugin. This can be done from the JetBrains plugins repository in TeamCity or by downloading the zip manually and adding it in the Web UI or locally in the TeamCity data directory.

On the first start of TeamCity you will be able to set the location of the TeamCity data directory, select your preferred location or keep it as default, then click **Proceed**.

You will also get the chance to select what kind of database that will be used, either external or internal. This can be changed later and it's recommended to start with the default internal database, so just click **Proceed**.

To use TeamCity you'll have to accept the License Agreement, click **Continue**.

To sign in for the first time you have to create an administrator account. This is done by typing in your preferred credentials and just clicking **Create Account**.

### Configuration

In the TeamCity client, click **Administration** --> **Projects** --> **Create project**.
![alt text](/images/createproject.gif "How to start creating a project")

Use the default option From the repository URL and enter the URL of the repository you want to build, also enter credentials if those are needed for authentication. Feel free to use this repo for this tutorial. Click **Proceed**.
![alt text](/images/repourl.gif "Enter repo url")

Next, you'll get the chance to name your prject and build. When done, click **Proceed**
![alt text](/images/proceed.gif "Project and build name")

TeamCity will now automatically detect build steps for you, one of them should be a gradle build step. Select it and then click **Use selected**. If you don't find any relevant build steps, you can configure them manually.
![alt text](/images/autodetect.gif "Auto detected build step")

When ready to build the project, just click **Run** below **Adminstration**.
![alt text](/images/run.gif "Run that thing")

## Quickguide

- Download: [TeamCity](https://www.jetbrains.com/teamcity/download/#section=section-get)

- Navigate to bin folder and run ```./runAll.sh start``` or ```sh runAll.sh start```.

- http://localhost:8111/
