# Description
Super parent pom with a meaningful set of pre-configured plugins:
 - maven compiler: eclipse compiler
 - gpg
 - build-helper
 - buildnumber
 - sources/javadoc/jar
 - dependency: report and fail in case of un-used dependency declarations
 
2 additional profiles exists for release and patch procedure:
 - release version: format ```${major}.${minor}.${incremental}-RELEASE```
 - patch version: format ```${major}.${minor}.${incremental}-patch-${0..N}```
