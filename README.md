# Reading-Task-4 - The Twelve-Factor App

The twelve factors are listed below, and I have re-arranged them in accordance with my own prioritization.
Summary of each point can be found at: https://12factor.net/

* I. Codebase
Keeping Codebase in the 1st place seems obvious. Keeping the code for the application in a VCS like git is the first step when you start a new project. We can track our code, revert back from new commits/pushes and makes it easier for a dev team to work on the same project.

* II. Dependencies
Keeping dependencies in a manifest file (Maven with its pom.xml in Java) makes sure we don't have to download and add JARs into different places in our codebase. With this approach of using a manifest file, we ensure that the project always uses the same version, and only one version of any dependency we might add.

* III. Config
Config keeps the 3rd place because any code we put on github, or otherwise make public in some form to the world should not have sensitive data, or credentials inside it which could cause harm. These properties should be put in a separate file that is referenced in the code.

* X. Dev/prod parity
I have moved dev/prod parity up a few ranks because of the unforeseen nature of running software on different platforms having unforeseen consequences at unfortunate times. We might develop and run our application on windows and deploy on ubuntu, and everything seems to work, but sometime down the line it suddenly doesn't work on ubuntu anymore because of some platform specific reason. We should avoid this as much as possible by building/running our code in an environment that matches the production environment as much as possible.

* IV. Backing services


* V. Build, release, run

* VI. Processes

* VII. Port binding

* VIII. Concurrency

* IX. Disposability

* XI. Logs

* XII. Admin processes



### Bibliography
https://dzone.com/articles/the-twelve-factor-app-what-it-is-and-how-to-monito

https://medium.com/hashmapinc/how-i-use-the-twelve-factor-app-methodology-for-building-saas-applications-with-java-scala-4cdb668cc908

https://12factor.net/

https://www.geeksforgeeks.org/what-is-twelve-factor-app/
