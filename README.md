CAS4 Services Management Web Application Maven overlay
============================

Services mangement web application Maven overlay for CAS versions `4.1.0+` with externalized configuration.

## NOTICE
**THIS PROJECT IS NOT CURRENTLY MAINTAINED NOR SUPPORTED**


# Versions
```xml
<cas.version>4.1.0-RC2</cas.version>
```

# Recommended Requirements
* JDK 1.7+
* Apache Maven 3+
* Servlet container supporting Servlet 3+ spec (e.g. Apache Tomcat 7+)

# Externalized Configuration
The `etc` directory contains the sample configuration files that would need to be copied to an external file system location (`/etc/cas` by default)
and configured to satisfy local CAS installation needs. Current files are:

* `cas-management.properties`
* `user-details.properties`
* `services/ServicesManagementWebApplication-52497044623301.json`

Note that the `log4j2.xml` config file is shared with cas web context and that file should be present already in `/etc/cas` directory.

# Deployment

## Maven
* Execute `mvn clean package`
* Deploy resultant `target/cas-services.war` to a Servlet container of choice (next to a running cas server)

# Use
Access the server on `https://localhost:8443/cas-services` (replace `localhost` and port with whatever your local deployment configuration is)
and start adding services definitions. Also note that the CAS server services registry MUST be JSON and pointing to the same external config
location for services files as this application. That setting would be in `/etc/cas/cas.properties` and should look like this: `service.registry.config.location=file:/etc/cas/services`
This same property is set in `/etc/cas/cas-management.properties` for this application.
