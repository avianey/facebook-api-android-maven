## Facebook Android SDK for Maven & Gradle

Current port is based on the v3.18.0 available at https://developers.facebook.com/android/  
The API is packaged as an **aar** and available from Maven Central Repository for use with **Maven** or **Gradle**.  

[![](https://coinbase.com/assets/buttons/donation_large-6ec72b1a9eec516944e50a22aca7db35.png)](https://coinbase.com/checkouts/0c34d3ca1be50e54a20bc83446b4db00)

###How to use

####Maven

The **aar** dependency requires the use of the maven-android-plugin 3.8.1+ with maven 3.1.1+ :

```xml
<dependency>
  <groupId>fr.avianey</groupId>
  <artifactId>facebook-android-api</artifactId>
  <version>3.18.0</version>
  <type>aar</type>
</dependency>
```

If you want to use a newer version of the android-support-v4 dependency, exclude the old one with this line :    

```xml
<dependency>
  <groupId>fr.avianey</groupId>
  <artifactId>facebook-android-api</artifactId>
  ...
  <exclusions>
    <exclusion>
      <artifactId>support-v4</artifactId>
      <groupId>com.google.android</groupId>
    </exclusion>
  </exclusions>
</dependency>
```

You might want to add the **jar** dependency as well to support code completion in Eclipse ADT. Adding the **jar** will result in **DEX** errors at build time as the Facebook API classes will be added twice to the generated **apk**. To solve the problem, build your project from command line and reference the **jar** dependency in the **m2e** (Eclipse only) Maven profile :  

```xml
<profiles>
  <profile>
    <id>m2e</id>
    <activation>
      <property>
        <name>m2e.version</name>
      </property>
    </activation>
    <dependencies>
      <dependency>
        <groupId>fr.avianey</groupId>
        <artifactId>facebook-android-api</artifactId>
        <version>3.18.0</version>
        <type>jar</type>
        <exclusions>
          <exclusion>
            <artifactId>support-v4</artifactId>
            <groupId>com.google.android</groupId>
          </exclusion>
        </exclusions>
      </dependency>
    </dependencies>
  </profile>
</profiles>
```

####Gradle

Add the following dependency to your build.gradle

```javascript
dependencies {
  compile 'fr.avianey:facebook-android-api:+@aar'
  // other dependencies
}
```

If you want to use a newer version of the android-support-v4 dependency, exclude the old one with this line :  

```javascript
configurations.all {
  exclude group: 'com.google.android', module: 'support-v4', version: 'r7'
  // other configurations
}
```
