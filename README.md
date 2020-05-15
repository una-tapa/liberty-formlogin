# SampleFormLogin

This is an experimental project to play with Form Login with WebSphere Liberty.

## How to compile

To clean the directories
`./gradlew cleanDirs`

To recompile the application.
`./gradlew libertyPackage`

To start/stop liberty
`./gradlew libertyStart`
`./gradlew libertyStop`

Logs are found in 
`build/wlp/usr/servers/defaultServer/logs/messages.log`

---
## How to run

It may be better to use firefix as Chrome usually does not allow non-CA certs. 

Login Panel: https://hirokos-mbp:9443/SampleFormLogin/login.html
![login](https://github.com/una-tapa/liberty-formlogin/blob/master/screenshots/login.png)

Context root: https://hirokos-mbp:9443/SampleFormLogin/login.html
![contextroot](https://github.com/una-tapa/liberty-formlogin/blob/master/screenshots/contextroot.png)

```
Error 404: SRVE0190E: File not found: /
```
Protected page: https://hirokos-mbp:9443/SampleFormLogin/HelloIBM
![protectedpage](https://github.com/una-tapa/liberty-formlogin/blob/master/screenshots/cat.png)

This page is only shown after successful authentication/authorization. 

---
## Note: Finding port conflict

This is just for me to remember... 
```
lsof -i tcp:9443
COMMAND   PID                USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
java    71569 htakamiy@us.ibm.com  140u  IPv6 0x686728a99ce8d815      0t0  TCP *:tungsten-https (LISTEN)

kill -9 71569
```

