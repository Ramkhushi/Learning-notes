## Apache Tomcat
- [ ]  How to Install Tomcat
```
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.76/bin/apache-tomcat-9.0.76.tar.gz
```
- [ ]  Untar using below command

```
tar -xvf apache-tomcat-9.0.76.tar.gz
```
- [ ] Move to the Apache unzipped folder

```
 cd apache-tomcat-9.0.76
 ```

- [ ]  Add the below lines
```
vi ./conf/tomcat-users.xml

 <role rolename="admin-gui,manager-gui,manager-script,manager-jmx,manager-status,admin-gui"/>
  <user username="admin" password="admin" roles="manager-gui,admin-gui,manager-script"/>
  <user username="robot" password="admin" roles="manager-script"/>
```

- [ ] Comment two lines in context.xml or remove 
```
vi  ./webapps/manager/META-INF/context.xml 

<!-- <Valve className="org.apache.catalina.valves.RemoteAddrValve"
  allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->
```
- [ ] Stop and start tomcat
```
./bin/shutdown.sh
./bin/startup.sh
```
- [ ] Check your tomcat if accessible from UI

```
ip:port
```
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/6785ad6d-3ba5-4649-a31a-6c9a02ba83c6)

----
Now you can also perform the deployment from there 





 ## Use Jenkins to deploy to container.

 - [ ] Install plugins
