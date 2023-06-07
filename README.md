# Description
Super parent pom with a meaningful set of pre-configured plugins:
 - maven compiler: eclipse compiler
 - gpg
 - build-helper
 - buildnumber
 - sources/javadoc/jar
 - dependency: report and fail in case of un-used dependency declarations
 
3 additional profiles exists for release and patch procedure:
 - release version: format ```${major}.${minor}.${incremental}-RELEASE```
 - patch version: format ```${major}.${minor}.${incremental}-patch-${0..N}```
 - gpg sign profile: automatically activated on release
 
 # How to use
 Artifact is available in central nexus repository, so just set parent as following:
 ```
 <parent>
    <groupId>com.turbospaces</groupId>
    <artifactId>turbospaces-parent-pom</artifactId>
    <version>10</version>
</parent>
 ```
 
 and then activate various plugins, most likely you would like to do the following:
 ```
<build>
   <plugins>
      <plugin>
         <groupId>org.codehaus.mojo</groupId>
         <artifactId>build-helper-maven-plugin</artifactId>
      </plugin>
      <plugin>
         <groupId>org.codehaus.mojo</groupId>
         <artifactId>buildnumber-maven-plugin</artifactId>
      </plugin>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-source-plugin</artifactId>
      </plugin>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-dependency-plugin</artifactId>
      </plugin>
   </plugins>
</build>
 ```
