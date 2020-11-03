# fixing-neo4j-issue-for-bloodhound

### Error:
[Java error](https://imgur.com/Fl3rPPI)

1. Install JDK 11 by registering to oracle and downloading the installer from this link: https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html
2. If errors still persist after installing java, fix it by modifying `Get-Java.ps1` powershell script which looks for the Java version, and point the $javaPath variable to the JDK 11 directory.

`$javaPath = 'C:\Program Files\Java\jdk-11.x.x\'`

Should be fixed now.

# fixing LinkedIt tool install errors

1. Remove 
2. pip2.7 install thready
