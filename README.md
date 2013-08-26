The mavenized Facebook Android API
==================================

Current port is based on the v3.5 available at https://developers.facebook.com/android/  

To use it in your Android Maven projects you need to add the following repository and dependency to your project pom.xml.  

The repository :  

    <repositories>  
      ...  
      <repository>  
        <id>The mavenized Facebook Android API</id>  
        <url>http://avianey.github.io/facebook-api-android-maven/</url>  
      </repository>  
    </repositories>

The dependency :  

    <dependencies>
      ...
      <dependency>
        <groupId>com.github.avianey</groupId>
        <artifactId>facebook-android-api</artifactId>
        <version>3.5</version>
        <type>apklib</type>
      </dependency>
    </dependencies>

The groupId com.github.avianey was picked to avoid conflicts with other third parties ports published in open repositories.  

If you want to use a different version for the android-support-v4 dependency you just have to exclude the import like this :  

    <dependencies>
      ...
      <dependency>
        <groupId>com.github.avianey</groupId>
        <artifactId>facebook-android-api</artifactId>
        <version>3.5</version>
        <type>apklib</type>
        <exclusions>
          <exclusion>
            <artifactId>support-v4</artifactId>
            <groupId>com.google.android</groupId>
          </exclusion>
        </exclusions>
      </dependency>
    </dependencies>
