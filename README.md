# Reading-Task-4 - The Twelve-Factor App

The twelve factors are listed below, and I have re-arranged them in accordance with my own prioritization.
Summary of each point can be found at: https://12factor.net/

* I. Codebase\
Keeping Codebase in the 1st place seems obvious. Keeping the code for the application in a VCS like git is the first step when you start a new project. We can track our code, revert back from new commits/pushes and makes it easier for a dev team to work on the same project.

* II. Dependencies\
Keeping dependencies in a manifest file (Maven with its pom.xml in Java) makes sure we don't have to download and add JARs into different places in our codebase. With this approach of using a manifest file, we ensure that the project always uses the same version, and only one version of any dependency we might add.

* III. Config\
Config keeps the 3rd place because any code we put on github, or otherwise make public in some form to the world should not have sensitive data, or credentials inside it which could cause harm. These properties should be put in a separate file that is referenced in the code.

* X. Dev/prod parity\
I have moved dev/prod parity up a few ranks because of the unforeseen nature of running software on different platforms having unforeseen consequences at unfortunate times. We might develop and run our application on windows and deploy on ubuntu, and everything seems to work, but sometime down the line it suddenly doesn't work on ubuntu anymore because of some platform specific reason. We should avoid this as much as possible by building/running our code in an environment that matches the production environment as much as possible.

* IV. Backing services\
Can be webservices, databases, message brokers and so on. They are all considered as resources and are loosely coupled. Twelve-Factor advocates that when changing from one service to another, there should be no code changes, only configurations. It is still an important part, which is why I've ranked it 4th.

* V. Build, release, run\
A Twelve-Factor application should have a clear distinction bewteen build, release, and run. In the case of Java, we build our project, bundling it with Maven into a JAR in the first step, build. In release we take our build, assign it a release number and prepare it for execution on the environment. In run we execute the build.

* VI. Processes\
We want our application to be stateless. With a stateless application we can start multiple instances of the same app, without worrying about which instance the user is communication with, as we do not want persisted data (session data). If we need to persist some data we should use a database. With statelessness we also achieve higher response times, if we have a lot of traffic as we can load balance between our instances.

* VII. Port binding\
Our application should be self-contained, and not rely on a running server to get executed.

* VIII. Concurrency\
An application that follows this principle must be divided into smaller different processes instead of a single large application. Each such process must be able to start, terminate and replicate itself independently and at any time<sup>1</sup>.

* XI. Logs\
Logs are treated like event streams. This helps us debug our code to see when some of our functionality broke, or didn't get called correctly, which is why I've moved 'Logs' up from second to last place.

* IX. Disposability\
The application should have a fast start-up and graceful shutdown in case of a crash. 

* XII. Admin processes\
If we need to run some sort of admin process, like database migration, these should be run before the application as a one-time process.


### Bibliography
https://dzone.com/articles/the-twelve-factor-app-what-it-is-and-how-to-monito

https://medium.com/hashmapinc/how-i-use-the-twelve-factor-app-methodology-for-building-saas-applications-with-java-scala-4cdb668cc908

https://12factor.net/

1. https://www.geeksforgeeks.org/what-is-twelve-factor-app/
