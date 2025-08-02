### 下载

1. Homebrew （MacOS）

```shell
brew install tomcat
```

2. 手动下载

- https://tomcat.apache.org/download-11.cgi
- Binary Distributions
	- Core
		- [zip](https://dlcdn.apache.org/tomcat/tomcat-11/v11.0.9/bin/apache-tomcat-11.0.9.zip)

### 目录介绍

- bin - 可执行文件目录，如startup, shutdown
- conf - 配置文件
- lib - tomcat的依赖jar包
- logs - 日志文件
- temp - 临时文件
- webapps - 应用发布目录
- work - 工作目录

### 启动

#### windows

> 前置条件：必须要配置 JAVA_HOME

直接点击运行`./bin/startup.bat`文件即可启动tomcat。

#### MacOS

1. 给可执行文件目录进行授权

```shell
cd tomcat/bin # 请替换为tomcat压缩包解压缩的文件目录

sudo chmod 755 *.sh
```

2. 启动

```shell
./startup.sh
```

#### 验证

在浏览器中访问： http://localhost:8080

如果显示tomcat的界面，则表示tomcat启动成功了。

### 解决 windows 启动控制台乱码

1. 找到`conf/logging.properties`文件并打开
2. 找到`java.util.logging.ConsoleHandler.encoding = UTF-8`
3. 将后面的`UTF-8`改成`GBK`即可

### 如何修改 tomcat 的端口

1. 找到`conf/server.xml`文件并打开
2. 找到以下配置：
```xml
<Connector port="8080" protocol="HTTP/1.1"
		   connectionTimeout="20000"
           redirectPort="8443" />
```
3. `8080`就是 tomcat 的默认端口，将其改成要修改的值即可

> 注意： HTTP协议的默认端口是 `80`, 如果我们将 tomcat 的端口修改为 `80`, 则可以直接通过 `http://localhost`来访问 tomcat

