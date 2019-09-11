# 安装wget命令
如果需要通过使用wget命令，直接通过网络下载maven安装包时，需要在linux系统中安装wget命令。
yum -y install wget

# 下载maven安装包
wget http://mirror.bit.edu.cn/apache/maven/maven-3/3.5.2/binaries/apache-maven-3.5.2-bin.tar.gz

# 解压缩maven
tar -zxvf apache-maven-3.5.2-bin.tar.gz 
我这里将maven解压缩之后的路径为：/root/davinx

# 配置maven环境变量
vi /etc/profile
添加环境变量
export MAVEN_HOME=/root/davinx/apache-maven-3.5.2
export MAVEN_HOME
export PATH=$PATH:$MAVEN_HOME/bin
编辑之后记得使用source /etc/profile命令是改动生效。

# 验证结果

在任意路径下执行mvn -version验证命令是否有效。
正常结果如下，能够看到当前maven及jdk版本。

![image](https://github.com/davinx594/image/blob/master/linux1.png）
![image](http://git.cn-hangzhou.oss-cdn.aliyun-inc.com/uploads/rds/schema_scripts/5cbf42922f8c36db27d617b8b32257b3/image.png)
# maven常见命令解析
## 1）把本地jar安装到maven本地仓库中：
+ a.命令如下:
mvn install:install-file -Dfile=c:\kaptcha-2.3.jar -DgroupId=com.google.code -DartifactId=kaptcha -Dversion=2.3 -Dpackaging=jar
+ b.在pom.xml使用如下：

> <dependency>
      <groupId>com.google.code</groupId>
      <artifactId>kaptcha</artifactId>
      <version>2.3</version>
 </dependency>
 
## 2）从 Maven 模板创建一个项目

+ a.从 maven-archetype-quickstart 模板创建 Java 项目:

mvn archetype:generate -DgroupId=com.aliyun -DartifactId=NumberGenerator -DarchetypeArtifactId=maven -archetype-quickstart -DinteractiveMode=false

使用mvn eclipse:eclipse命令转换成eclipse可直接导入项目

+ b.从maven-archetype-webapp模板来创建一个快速启动Java Web应用程序的项目

mvn archetype:generate -DgroupId=com.aliyun  -DartifactId=MavenWebApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false

使用mvn eclipse:eclipse -Dwtpversion=2.0命令转换成eclipse可直接导入项目
