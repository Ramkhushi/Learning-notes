#### ELK Stack

- [ ] Login to Lab Vm  and run below command

```
sudo -s
cd
```

- [ ] Download and Install Elasticsearch using below command

```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.8.23.deb

dpkg -i elasticsearch-6.8.23.deb

```
 - [ ] Started Es service

```
systemctl start elasticsearch
systemctl enable elasticsearch
```
- [ ] Test Es using below command

```
curl localhost:9200
```
- [ ] Download and Install kibana 

```
wget https://artifacts.elastic.co/downloads/kibana/kibana-6.8.23-amd64.deb

dpkg -i kibana-6.8.23-amd64.deb

systemctl restart kibana
systemctl enable kibana 
```
- [ ] Open kibana in browser

```
localhost:5601
```


- [ ] Download and install filebeat

```
wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-6.8.23-amd64.deb
dpkg -i filebeat-6.8.23-amd64.deb
```
- [ ] Modify /etc/filebeat/filebeat.yaml as below highlighted 

![image](https://user-images.githubusercontent.com/120269399/234763413-ec9a36cd-4835-4b63-b9be-1e78cca22900.png)

- [ ]  Add Dashboard block as well if needed 

![image](https://user-images.githubusercontent.com/120269399/234763696-ab868776-b64d-4cf3-bb64-e0fa8cb5dab9.png)


##NOTE: Same configuration can be done for metricbeat/heartbeat etc


- [ ] Restart filebeat svc

```
systemct restart filebeat
systemctl status filebeat
systemct enable filebeat
```

- [ ] Test the configuration for filebeat

```
filebeat test config
filebeat test output
```

 
