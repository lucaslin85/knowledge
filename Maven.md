##模块版本统一管理
```
1.父工程中统一定义 properties: revision
<properties>
        <revision>1.0.0-SNAPSHOT</revision>
</properties>

2.工程的版本version 引用 revision

eg:
 >>>parent pom :
 
 <?xml version="1.0" encoding="UTF-8"?>
 <project xmlns="http://maven.apache.org/POM/4.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
     <modelVersion>4.0.0</modelVersion>
 
     <groupId>com.guiysoft</groupId>
     <artifactId>parent</artifactId>
     <name>project parent pom</name>
     <packaging>pom</packaging>
     <version>${revision}</version>
 
     <properties>
         <revision>1.0.0-SNAPSHOT</revision>
     </properties>
 </project>
 
 >>>module pom : 
  
 <?xml version="1.0" encoding="UTF-8"?>
 <project xmlns="http://maven.apache.org/POM/4.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
     <modelVersion>4.0.0</modelVersion>
 
     <groupId>com.guiysoft</groupId>
     <artifactId>module-1</artifactId>
     <version>${revision}</version>
     <parent>
         <groupId>com.guiysoft</groupId>
         <artifactId>parent</artifactId>
         <version>${revision}</version>
         <relativePath>../parent/pom.xml</relativePath>
     </parent>
 </project>
 
```