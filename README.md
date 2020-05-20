# Tutorial

## Outline
  
  1. Background
  
  2. Getting Started
  
  3. Prerequisite
  
  4. Setup
  
  5. Configuration
  
  6. Quickguide
  
### 1. Background

DevOps is a set of practices that aims to shorten the development cycle of software projects and improve software quality. Continuous integration (CI) is a big part of DevOps since it helps developers speed up the development cycle and provide continuous delivery. Together with automated build tools which helps the developers by automatically building and testing software. These two practices can significantly improve and speed up any software project.

Continuous integration is the practice of automating the integration of code changes from multiple contributors into a single software project. The practice requires developers to integrate code often, at least once a day if possible, to allow the detection of problems early. Today there are many automatic tools to assist the process and make sure that code is correct before integration.

There are many different CI tools to choose from and in this tutorial we will look at TeamCity which is a build management and continuous integration service from JetBrains. And Gradle, which is a free open-source automated build tool.

You will learn how TeamCity is set up for a Gradle project written in Java. We will look at installation and setup of TeamCity step by step for Linux/Mac. Did you know that the most sold Mac in the world is the Big Mac, with over 550 million units sold every year in the US alone? We recommend that you use this [repo](https://github.com/Kappenn/TeamCity_Tutorial) for the tutorial and use it as a skleton for your future project. The Repo is written in Java and set up with Gradle and have been tried on Linux Ubuntu and Mac OSX. Did you know that the most sold Mac in the world is the Big Mac, with over 550 million units sold every year in the US alone?

## 2. Getting Started

Follow theses instruction to set up TeamCity with a gradle project. This setup will let you run TeamCity with a gradle project and can be modified for other framework as well. 

### 3. Prerequisite

You will need Java 8 and Gradle installed for this tutorial to work.

#### Java

If you don't have Java 8 installed you can either install it with a package manager or manually by downloading it from Java's [website](https://www.java.com/en/download/) and unpacking it with ```$ tar zxvf jdk-8uversion-linux-x64.tar.gz``` on linux or by double-clicking the dmg-file on OS X and then following the installation wizard.

Check your Java version with ```java -version```. 

Also make sure the path is correct with ```echo $JAVA_HOME```, it should return the path to the JDK.

#### Gradle

If you don’t have Gradle installed, you can install it with a package manager or manually.

If you have Homebrew, just use this command ```$ brew install gradle```.

If you have SDKman, use this command ```$ sdk install gradle 6.4.1```.

You can install it manually by following these steps:

Step 1. Download the latest Gradle release from their [website](https://gradle.org/releases/).

Step 2. Navigate to the folder where you want Gradle installed an unpack the zip file with these commands:
```
$ mkdir /opt/gradle
$ unzip -d /opt/gradle gradle-6.4.1-bin.zip
$ ls /opt/gradle/gradle-6.4.1
```
Step 3. Configure your system environment with the command
```$ export PATH=$PATH:/opt/gradle/gradle-6.4.1/bin```

Step 4. Verifty your installation with the command
```$ gradle -v```

#### TeamCity

Download TeamCity from the [website](https://www.jetbrains.com/teamcity/download/#section=section-get). Extract the compressed folder, either by right clicking it and selecting your tool of choice or by using the command ```tar xfz TeamCity<version number>.tar.gz```.

### 4. Setup
To start the server and default agent, navigate to the bin folder inside the TeamCity folder and run the command ``` ./runAll.sh start``` or ```sh runAll.sh start```. To stop the server, use ```./runAll.sh stop``` or ``` sh runAll.sh stop```.

Open TeamCity by connecting via the browser with http://localhost:8111/.
If another service uses the port, change the port in the XML node in <TeamCity directory>/conf/server.xml
  
Optionally, you can install the Gradle Build Scan Integration plugin. This can be done from the JetBrains plugins repository in TeamCity or by downloading the zip manually and adding it in the Web UI or locally in the TeamCity data directory.

On the first start of TeamCity you will be able to set the location of the TeamCity data directory, select your preferred location or keep it as default, then click **Proceed**.

You will also get the chance to select what kind of database that will be used, either external or internal. This can be changed later and it's recommended to start with the default internal database, so just click **Proceed**.

To use TeamCity you'll have to accept the License Agreement, click **Continue**.

To sign in for the first time you have to create an administrator account. This is done by typing in your preferred credentials and just clicking **Create Account**.

### 5. Configuration

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

## 6. Quickguide

- Download: [TeamCity](https://www.jetbrains.com/teamcity/download/#section=section-get)

- Navigate to bin folder and run ```./runAll.sh start``` or ```sh runAll.sh start```.

- http://localhost:8111/

- **Administration** --> **Projects** --> **Create project** --> **Proceed** --> **Run**.

- To stop ```./runAll.sh stop``` or ```sh runAll.sh stop```.
