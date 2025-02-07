
## Installation

-> Install an App -> Tomcat10
-> ./usr/local/apps/tomcat10/bin/startup.sh
-> nano /usr/local/apps/tomcat10/webapps/manager/META-INF/context.xml
```xml
<Context antiResourceLocking="false" privileged="true" >
    <!--
    <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" />
    -->
</Context>
```

## Permissions 

-> nano  /usr/local/apps/tomcat10/conf/tomcat-users.xml 
  ```xml 
  <user username="admin" password="DEIN_PASSWORT" roles="manager-gui"/>
  ```
  
Maximale Upload-Filesize erhöhen
-> sudo nano usr/local/apps/tomcat10/webapps/manager/WEB-INF/web.xml
  ```xml
<servlet>
    <servlet-name>HTMLManager</servlet-name>
    <servlet-class>org.apache.catalina.manager.HTMLManagerServlet</servlet-class>
    <multipart-config>
        <max-file-size>52428800</max-file-size>        <!-- 50 MB -->
        <max-request-size>52428800</max-request-size>  <!-- 50 MB -->
        <file-size-threshold>0</file-size-threshold>
    </multipart-config>
</servlet>
```

## Server Start / Stop

-> ./usr/local/apps/tomcat10/bin/startup.sh
-> ./usr/local/apps/tomcat10/bin/shutdown.sh

## Wipe cache

-> rm -rf /usr/local/apps/tomcat10/work/Catalina/localhost/*

## Logs

Logs auslesen
-> cat /usr/local/apps/tomcat10/logs/catalina.out

Logs löschen
-> echo "" > /usr/local/apps/tomcat10/logs/catalina.out 

## Config

-> nano  /usr/local/apps/tomcat10/conf/context.xml
