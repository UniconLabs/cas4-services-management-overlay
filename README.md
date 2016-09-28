CAS Services Management Overlay
============================

Services management web application Maven overlay for CAS with externalized configuration.


# Versions
```xml
<cas.version>5.0.0</cas.version>
```

# Requirements

* JDK 1.8+

# Build

```bash
build.sh run

```


# Deployment

## Embedded Tomcat

CAS will be available at:

* `http://cas.server.name:8080/cas-management`
* `https://cas.server.name:8443/cas-management`

## External

Deploy resultant `target/cas-management.war`  to a servlet container of choice.