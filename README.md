The Facebook Android SDK for Maven & Gradle
===========================================

Current port is based on the v3.6.0 available at https://developers.facebook.com/android/  
The API is packaged as an **aar** and available from Maven Central Repository for use with **Maven** or **Gradle**.

##How to use

###Maven

The **aar** dependency requires the use of the maven-android-plugin 3.8.1+ with maven 3.1.1+ :

```xml
<dependency>
  <groupId>fr.avianey</groupId>
  <artifactId>facebook-android-api</artifactId>
  <version>3.6.0</version>
  <type>aar</type>
</dependency>
```

If you want to use a different version for the android-support-v4 dependency you just have to exclude the import like this :  

```xml
<dependency>
  <groupId>fr.avianey</groupId>
  <artifactId>facebook-android-api</artifactId>
  <version>3.6.0</version>
  <type>aar</type>
  <exclusions>
    <exclusion>
      <artifactId>support-v4</artifactId>
      <groupId>com.google.android</groupId>
    </exclusion>
  </exclusions>
</dependency>
```

###Gradle

Add the following dependency to your build.graddle

```javascript
dependencies {
  compile 'com.facebook:facebook-android-sdk:+@aar'
  // other dependencies
}
```

If you want to use a different version for the android-support-v4 dependency you just have to exclude the import like this :  

```javascript
configurations.all {
  exclude group: 'com.google.android', module: 'support-v4', version: 'r7'
  // other configurations
}
```
