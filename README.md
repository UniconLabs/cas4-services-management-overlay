CAS Services Management Overlay
============================

Services management web application Maven overlay for CAS with externalized configuration.


# Versions
```xml
<cas.version>4.2.1</cas.version>
```

# Recommended Requirements
* JDK 1.7+

# Externalized Configuration
The `etc` directory contains the sample configuration files that would need to
be copied to an external file system location (`/etc/cas` by default)
and configured to satisfy local CAS installation needs. Current files are:

* `cas-management.properties`
* `user-details.properties`
* `services/ServicesManagementWebApplication-52497044623301.json`

Note that the `log4j2.xml` config file is shared with cas web context and that
file should be present already in `/etc/cas` directory.

# Build

```bash
mvnw clean package
```

or

```bash
mvnw.bat clean package
```

# Deployment

## Embedded Jetty

* Create a Java keystore at `/etc/cas/jetty/thekeystore` with the password `changeit`.
* Import your server certificate inside this keystore.

```bash
mvnw jetty:run-forked
```

Webapp will be available at:

* `http://localhost:8080/cas-services`
* `https://localhost:8443/cas-services`

## External
Deploy resultant `target/cas-services.war` to a Servlet container of choice.

# Use
Access the server on `https://localhost:8443/cas-services`
and start adding services definitions. Also note that the CAS server services
registry MUST be JSON and pointing to the same external config
location for services files as this application.
That setting would be in `/etc/cas/cas.properties` and
should look like this: `service.registry.config.location=file:/etc/cas/services`
This same property is set in `/etc/cas/cas-management.properties`
for this application.
