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

Resources
---------

* https://maven.apache.org/plugins/maven-war-plugin/overlays.html
* https://jolokia.org/
