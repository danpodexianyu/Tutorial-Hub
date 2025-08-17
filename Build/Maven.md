# Maven

**JDK**： 21
**Maven**： 3.9.11 (Maven 3.9+ requires JDK 8 or above to execute)

### 一、下载

官网下载地址： https://maven.apache.org/download.cgi
![[maven_download.png]]

### 二、安装

**前置条件**：安装 maven 之前需要安装 JDK，并且正确配置JAVA_HOME。
**软件安装**：将下载的压缩包解压即可

### Maven 环境变量配置

1. 配置 MAVEN_HOME
![[maven_home.png]]
2. 配置 path：%MAVEN_HOME%
![[maven_path.png]]
3. 验证：进入命令行输入 `mvn -v`

![[maven_verify.png]]

### 三、配置

1. 配置本地仓库地址

```xml
<!-- localRepository
The path to the local repository maven will use to store artifacts.
|
| Default: ${user.home}/.m2/repository
<localRepository>/path/to/local/repo</localRepository>
-->
<localRepository>D:\DevTools\mvn_repo</localRepository>
```

2. 配置国内阿里镜像
```xml
<mirror>
  <id>alimaven</id>
  <name>aliyun maven</name>
  <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
  <mirrorOf>central</mirrorOf>        
</mirror>
```

3. 配置 jdk 编译版本
```xml
<profile>
	<id>jdk-21</id>
	<activation>
		<activeByDefault>true</activeByDefault>
		<jdk>21</jdk>
	</activation>
	<properties>
	    <maven.compiler.source>21</maven.compiler.source>  
	    <maven.compiler.target>21</maven.compiler.target>
	    <maven.compiler.compilerVersion>21</maven.compiler.compilerVersion>
	</properties>
</profile>
```

四、IDEA 配置本地 Maven

> 注意：IDEA 中默认自带 Maven，如果不进行配置，则所有的设置都将采用默认设置

File -> Settings -> Build, Execution, Deployment -> Build Tools -> Maven

![[maven_idea_configure.png]]