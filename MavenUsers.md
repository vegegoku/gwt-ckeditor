# Introduction #
It is now possible to use gwt-ckeditor with Maven. This integration allows users to use the latest released version, or nightly snapshots.


# Releases #

To use the Release version, add the Axeiya Release Repository :
```
<repositories>
  ...
  <repository>
    <id>axeiya</id>
    <url>http://nexus.axeiya.com/nexus/content/repositories/releases</url>
  </repository>
</repositories>
```
And add the dependency (provided because there is no runtime need)
```
<dependency>
  <groupId>com.axeiya.gwt</groupId>
  <artifactId>gwt-ckeditor</artifactId>
  <version>1.0</version>
  <scope>provided</scope>
</dependency>
```
# Snapshots #

Add the Axeiya Snapshots Repository :
```
<repositories>
  ...
  <repository>
    <id>axeiya</id>
    <url>http://nexus.axeiya.com/nexus/content/repositories/snapshots</url>
  </repository>
</repositories>
```
And add the dependency (provided because there is no runtime need)
```
<dependency>
  <groupId>com.axeiya.gwt</groupId>
  <artifactId>gwt-ckeditor</artifactId>
  <version>1.1-SNAPSHOT</version>
  <scope>provided</scope>
</dependency>
```
By default, it will use the latest snapshot from the repository ; you can enforce a specific version by using the classifier :
```
<dependency>
  <groupId>com.axeiya.gwt</groupId>
  <artifactId>gwt-ckeditor</artifactId>
  <version>1.1-SNAPSHOT</version>
  <scope>provided</scope>
  <classifier>20110626.084032-1</classifier>
</dependency>
```
Browse the repository to get specific snapshot name, etc.