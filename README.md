# fixing-neo4j-issue-for-bloodhound


[Java error](https://imgur.com/Fl3rPPI)

## Install JDK 11 by registering to oracle and downloading the installer from this link: https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html
## If errors still persist after installing java, fix it by modifying `[Get-Java.ps1](https://imgur.com/Ndr6jDI)` powershell script which looks for the Java version, and point the $javaPath variable to the JDK 11 directory.



