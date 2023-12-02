# Jenkins Basics

Jenkins Can be hosted in the following ways<br>

* By windows Service: That can be done by windows installer file
* By war : By Starting Jenkins server as a executable jar

## Starting Jenkins server as a executable jar and Configuration
a. Start the Jenkins Server by War file Commands
```cmd
cd C:\Program Files (x86)\Jenkins
java -jar Jenkins.war
```

b. Server Machine Configuration:
Initial Configuration of Windows system:
```
	1. JDK has to be installed: jdk-8u172-windows-x64.exeset Path
	2.  Maven has to be installed.[Donload Zip Place it in C:\Pograme Files\]set path
	3.  Git Has to be installed.
	4.  TortiseGit has to be installed. To pull the code
```
c. set User Variable:
```cmd
HOME   C:\Pogram Files\Jenkins\
JAVA_HOME C:\Program Files\Java\jdk1.8.0_181\
```

d. System Variable:
```cmd
M2_HOME  C:\Program Files\apache-maven-3.6.0
MAVEN_HOME C:\Program Files\apache-maven-3.6.0
```
e. Path:
```cmd
C:\Program Files\Java\jdk1.8.0_181\bin
C:\Program Files\apache-maven-3.6.0\bin
C:\Program Files\Git\cmd