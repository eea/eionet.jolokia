Preconfigured Jolokia module
============================

This is the Jolokia product from https://jolokia.org/. The only difference is that the `jolokia-access.xml` is modified to fit EEA needs.

The build is done using the Maven Overlay Method, so you only see the files that have been modified here. The rest is downloaded as dependencies
with Maven.

To update, change the jolokia.version number in the pom.xml or the jolokia-access.xml in src/main/resources and rebuild with:
```
mvn clean deploy
```

The war file can then be downloaded from http://archiva.eionet.europa.eu/ and placed in a Tomcat container.

Reverse proxying
----------------

In case there is a reverse proxy in front of the Tomcat application, then the access control has a line to allow a host called `reverseproxy` access. To use it you declare the host in /etc/hosts with the relevant IP number. In case you have dockerised your application, you use the `links` or `extra_hosts` in docker-compose.yml. `external_links` won't work because they don't get updated when the other container is restarted.

Resources
---------

* https://maven.apache.org/plugins/maven-war-plugin/overlays.html
* https://jolokia.org/
