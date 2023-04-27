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
