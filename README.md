# sample-bwce-pom
sample project with POM file

## Download from maven central :
* https://repo1.maven.org/maven2/com/tibco/plugins/bw6-maven-plugin/2.10.2/bw6-maven-plugin-2.10.2.jar
* https://repo1.maven.org/maven2/com/tibco/plugins/bw6-maven-plugin/2.10.2/bw6-maven-plugin-2.10.2.pom
* https://repo1.maven.org/maven2/io/fabric8/fabric8-maven-plugin/4.4.1/fabric8-maven-plugin-4.4.1.jar
* https://repo1.maven.org/maven2/io/fabric8/fabric8-maven-plugin/4.4.1/fabric8-maven-plugin-4.4.1.pom

## Copy the following files from you existing BW install to your CICD server
* C:\tibco\bwce/bwce/2.9/system/shared/com.tibco.bw.palette.shared_6.2.1901.001.jar
* C:\tibco\bwce/bwce/2.9/system/shared/com.tibco.xml.cxf.common_1.3.1900.002.jar
* C:\tibco\bwce/bwce/2.9/system/shared/org.osgi.service.jdbc_5.0.100.002/lib/org.osgi.service.jdbc-1.0.1.jar

## Install plugins using mvn install commands
```bash
mvn install:install-file -Dfile=com.tibco.bw.palette.shared_6.2.1901.001.jar -DgroupId=com.tibco.plugins -DartifactId=com.tibco.bw.palette.shared -Dversion=6.2.1901 -Dpackaging=jar
mvn install:install-file -Dfile=com.tibco.xml.cxf.common_1.3.1900.002.jar -DgroupId=com.tibco.plugins -DartifactId=com.tibco.xml.cxf.common -Dversion=1.3.1900 -Dpackaging=jar
mvn install:install-file -Dfile=org.osgi.service.jdbc-1.0.1.jar -DgroupId=com.tibco.plugins -DartifactId=org.osgi.service.jdbc -Dversion=5.0.100 -Dpackaging=jar
mvn install:install-file -Dfile=bw6-maven-plugin-2.10.2.jar -DpomFile=bw6-maven-plugin-2.10.2.pom
mvn install:install-file -Dfile=fabric8-maven-plugin-4.4.1.jar -DpomFile=fabric8-maven-plugin-4.4.1.pom
```


## Build your application
```bash
mvn clean install -f timer.application.parent/pom.xml
```