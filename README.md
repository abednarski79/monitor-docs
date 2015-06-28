Configuration 
-------------

Using pre-configured zip archive:
- create folder "C:\development"
- move archive to "C:\development" and unzip in that location
- please check if the following locations exist:
 - "C:\development\appbucket\tools\apache-activemq-5.11.0\bin"
 - "C:\development\appbucket\tools\hsqldb-2.3.2\hsqldb\bin"
 - "C:\development\appbucket\tools\tomcat\bin"
 - "C:\development\appbucket\projects\monitor-shared"
 - "C:\development\appbucket\projects\monitor-trigger"
 - "C:\development\appbucket\projects\monitor-web"
 - "C:\development\appbucket\projects\monitor-docs"

OR

Starting from scratch:
- activemq
 - download activemq archive from http://activemq.apache.org/ and install
 - go monitor-shared and monitor-trigger projects and follow the configuration in read-me file
- hsqldb
 - download from http://hsqldb.org/ and install
 - go monitor-shared and monitor-trigger projects and follow the configuration in read-me file
- monitor application
- checkout source file for the following repositories:
 - https://github.com/abednarski79/monitor-shared.git
 - https://github.com/abednarski79/monitor-trigger.git
 - https://github.com/abednarski79/monitor-web.git
 - follow the read-me files in above projects

Running
-------
Using pre-configured zip archive:
- activemq
 - open command line console and go to "C:\development\appbucket\tools\apache-activemq-5.11.0\bin" and execute command:
 - run.bat
- hsqldb
 - open command line console and go to "C:\development\appbucket\tools\hsqldb-2.3.2\hsqldb\bin" and execute command:
 - run.bat
- monitor application
 - open command line console and go to "C:\development\appbucket\tools\tomcat\bin" and execute command:
 - run.bat
- open web browser and go to "http://localhost:8080/monitor-web-1.0-SNAPSHOT/"
- open command line console and go to "C:\development\appbucket\tools\hsqldb-2.3.2\hsqldb\bin" and execute command:
 - runManagerSwing.bat
 - set as type "HSQL Database Engine Server" and as url jdbc:hsqldb:hsql://localhost/testdb
 - follow the read-me file from monitor-trigger project for examples of SQL queries - run them and observer the output on monitor web page
- to check health status of the application open web browser and go to "http://localhost:8080/monitor-web-1.0-SNAPSHOT/status"
- to check manifest version details open web browser and go to "http://localhost:8080/monitor-web-1.0-SNAPSHOT/manifest"
- to check message in the queue open web browser and to go to (use admin/admin credentials) "http://localhost:8161/admin/browse.jsp?JMSDestination=testqueue"

OR

Starting from scratch:
- activemq
 - start application according to the instruction on the web page
 - create testqueue in the activemq console
- hsqldb
 - start application according to the instruction on the web page with the exception that in the classpath 
must be included all jar files copied from monitor-shared and monitor-trigger projects according to their read-me files
 - create DB using scripts from read-me file in monitor-trigger

Stopping
--------
Using pre-configured zip archive:
- activemq
 - open command line console and go to location from which app was started and use Ctrl+C combination to shut down
- hsqldb
 - open command line console and go to location from which app was started and and execute command:
runManagerSwing.bat
 - set as type ...In-Memory and as url jdbc:hsqldb:hsql://localhost/testdb
 - select from menu Command -> SHUTDOWN
