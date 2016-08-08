CAS Services Management Overlay
============================

Services management web application Maven overlay for CAS with externalized configuration.


# Versions
```xml
<cas.version>5.0.0</cas.version>
```

# Requirements
* JDK 1.8+

# Configuration

The `etc` directory contains the configuration files and directories that need to be copied to `/etc/cas/config`.

# Build

```bash
mvnw[.bat] clean package && java -Xdebug -Xrunjdwp:transport=dt_socket,address=5000,server=y,suspend=n -jar target/cas-management.war 

```


# Deployment

## Embedded Tomcat

CAS will be available at:

* `http://cas.server.name:8080/cas-management`
* `https://cas.server.name:8443/cas-management`

## External
Deploy resultant `target/cas-management.war`  to a servlet container of choice.