# ![OWASP VulnerableApp](https://raw.githubusercontent.com/SasanLabs/VulnerableApp/master/docs/logos/Coloured/iconColoured.png) OWASP VulnerableApp

![OWASP Incubator](https://img.shields.io/badge/owasp-incubator-blue.svg) ![](https://img.shields.io/github/v/release/SasanLabs/VulnerableApp?style=flat) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![Java CI with Gradle](https://github.com/SasanLabs/VulnerableApp/workflows/Java%20CI%20with%20Gradle/badge.svg) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com) [![Docker Pulls](https://badgen.net/docker/pulls/sasanlabs/owasp-vulnerableapp?icon=docker&label=pulls)](https://hub.docker.com/r/sasanlabs/owasp-vulnerableapp/) [![codecov](https://codecov.io/gh/SasanLabs/VulnerableApp/graph/badge.svg?token=DTS3PA8WXZ)](https://codecov.io/gh/SasanLabs/VulnerableApp)

As Web Applications are becoming popular these days, there comes a dire need to secure them. Although there are several Vulnerability Scanning Tools, however while developing these tools, developers need to test them. Moreover, they also need to know how well the Vulnerability Scanning tool is performing. As of now, there are little or no such vulnerable applications existing for testing such tools. There are Deliberately Vulnerable Applications existing in the market but they are not written with such an intent and hence lag extensibility, e.g. adding new vulnerabilities is quite difficult. Hence, developers resort to writing their own vulnerable applications, which usually causes productivity loss and the pain of reworking.

**VulnerableApp** is built keeping these factors in mind. This project is scalable, extensible, easier to integrate and easier to learn.
As solving the above issue requires addition of various vulnerabilities, hence it becomes a very good platform to learn various security vulnerabilities.

### User Interface ###
![VulnerableApp-facade UI](https://raw.githubusercontent.com/SasanLabs/VulnerableApp-facade/main/docs/images/gif/VulnerableApp-Facade.gif)

## Technologies used
- Java8
- Spring Boot
- ReactJS
- Javascript/TypeScript
    
## Running the project
There are 2 ways to run the project:
1. The simplest way to run the project is using Docker containers which will run the full-fleged VulnerableApplication with all the components. For running as Docker application, follow following steps:
    1. Download and Install [Docker Compose](https://docs.docker.com/compose/install/) 
    2. Clone this Github repository
    3. Open the terminal and Navigate to the Project root directory
    4. Run the command ```docker-compose pull && docker-compose up```
    5. Navigate to browser and visit `http://localhost` and this will give the User Interface for VulnerableApp.
    
    **Note**: The above steps will run the latest unreleased VulnerableApp version. If you want to run the latest released version, please use docker **latest** tag.
2. Another way to run the VulnerableApp is as standalone Vulnerable Application is:
    1. Navigate to [Releases Section](https://github.com/SasanLabs/VulnerableApp/releases) in github and download the Jar for the latest released version
    2. Open the terminal and navigate to the project root directory
    3. Run the command ```java -jar VulnerableApp-*```
    4. Navigate to browser and visit `http://localhost:9090/VulnerableApp`. This will give the Legacy User Interface for the VulnerableApp.

## Building the project
There are 2 ways in which this project can be built and used:
1. As a Docker application which will help in running the full-fledged VulnerableApplication. For running as Docker application, follow following steps:
    1. Build the docker image by running `./gradlew jibDockerBuild`
    2. Download [Docker-Compose](https://github.com/SasanLabs/VulnerableApp-facade/blob/main/docker-compose.yml) and run in the same directory `docker-compose up`
    3. Navigate to browser and visit `http://localhost` and this will give the User Interface for VulnerableApp.
2. As a SpringBoot application which will run with the Legacy UI or Rest API but gives the benefit of debugging and solving issues. This is the simple way, 
    1. Import the project into your favorite IDE and run it
    2. Navigate to browser and visit: `http://localhost:9090/VulnerableApp` and this will give the Legacy User Interface for VulnerableApp which you can use to debug and test.
    
### Connecting to embedded H2 database
For accessing database from browser, visit: `http://localhost:9090/VulnerableApp/h2`

Database Connection properties:
```properties
JDBC Url: jdbc:h2:mem:testdb
User Name: admin
Password: hacker
```