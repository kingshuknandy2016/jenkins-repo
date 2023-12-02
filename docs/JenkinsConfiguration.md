## Java Project Setup with CI/CD
Here will create a basic ***Java Maven Project*** and push the code to ***github*** repository. Then setup jenkins job which will pull from the code from ***Git*** and execute the job

### Local System Setup
* Install Eclipse.
* Do git clone of the Repository
* Import the Project
* Install Testg in eclipse

### Plugins required
Maven Integration plugin Plugin for Maven feature.
HTML Publisher plugin for Report show
```
Git Plugins:   
a.Git Client Plugin
b.Git Plugin
c.Git Server Plugin
d.GitHub API Plugin
e.GitHub Branch Source Plugin
f.GitHub Plugin
```
      
### Global Tool Configuration
Maven
```
Maven
C:\Program Files\apache-maven-3.6.0
```
JDK:
```
JAVA_HOME
C:\Program Files\Java\jdk1.8.0_181\
```
Git
```
Name: Default
C:\Program Files\Git\bin
```

## Parameterized Job Setup Complete Configuration
1. Select Maven Project
2. Select Git Project and give the Git URL
3. Select, This project is parameterized
     choice parameters:
	Name : 
		language

		Choises:
		en_US
		es_ES

		Description: 
		en_US for English Language
		es_ES for Espanol Language
		
	Name: config
		testng_perfecto.xml
		testng_regression.xml
4. Source code management:
Git: Give the credentials and details including branch

Example
Repository URL  : https://github.com/userA/CheckerPOC.git
Credentials : SSH private keys  [C:\Program Files (x86)\Jenkins\.ssh]

Key Generation:
Install Git,
Open Git bash,
Run command: ssh-keygen -t rsa -C nandykingshuk1990@example.com

Add SSH public Keys into the GitHub
Git Hub Setting for WebHook:

5. Built Triggers:
	a)GitHub Hook Triggers for Git SCM Polling:::For Automatic Built Triggerring when a Built is pushed in GitHub
	b]Built Periodically:::For Timming scheduling

6. Built:pom.xml
	test
	
7. Post Built Actions:
Publish HTML reports::
		Indexpage: ABC.xml
Publish TestNG XML Report:**/**/testng-results.xml
<br/><br/>
Issues:
Go to Manage Jenkins > Script Console > enter value > System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "default-src * 'unsafe-inline' 'unsafe-eval';script-src 'self' 'unsafe-inline' 'unsafe-eval'"); > Click Run 2 times... it will work

## Katalon Integration:
[Article Link](https://dzone.com/articles/how-to-setup-the-integration-with-jenkins-and-other)

Windows Batch Command:
```cmd
cd C:\Users\king\.jenkins\workspace\Proj1
git pull proj1_url
cd C:\Users\king\Downloads\Katalon_Studio_Windows_64-6.2.0
katalon -noSplash  -runMode=console -projectPath="C:\Users\king\.jenkins\workspace\Proj1\abc_name.prj" -retry=0 -testSuitePath="Test Suites/%TestSuite_name%" -executionProfile="%Execution_Profile%" -browserType="%Browser%" -reportFolder="Reports\Details" -reportFileName="report" -apiKey=******************
echo Success
```

## Test Results Viewing
  Install Test Result Analyzer to View the Junit Report:
https://wiki.jenkins.io/display/JENKINS/Test+Results+Analyzer+Plugin


## Built Triggers Poll SCM:

Chron syntax: * * * * *
```cmd
1st * :Minute(0-59)
2nd * :Hour(0-23)
3rd * :Day of Month(1-31)
4th * :Month(1-12)
5th * :Day of Week(0-6)(Sunday = 0)
```
To specify Multiple values for 1 Feild:
```cmd
*      For all values
M-N    A range of values
A,B,Z  Enumerates multiple values
```

Examples:
```cmd
0 0 * * *     Every Day at Midnight
0 2-4 * * *   2 AM ,3 AM , 4 AM Every Day
```

## Code Quality and Code Coverage Metrix Report: Plugins
***Plugins***  : CheckStyle,PMD,FindBugs

* https://wiki.jenkins.io/display/JENKINS/Checkstyle+Plugin
* https://wiki.jenkins.io/display/JENKINS/PMD+Plugin
* https://wiki.jenkins.io/display/JENKINS/FindBugs+Plugin


