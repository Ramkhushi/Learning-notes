## Nagios Server Installation Steps

- [ ] Login to Lab VM and run below command

```
sudo -s
cd
```

- [ ] Update your OS
```
apt update
```

- [ ] Execute the below command to install Nagios and it will take 20 to 25 mins

```
curl https://assets.nagios.com/downloads/nagiosxi/install.sh | sh
```

In the end you will get url , user name and password to login 



### Adding Host to Nagios Server 

- [ ]	Navigate to Configure > Core config manager from the nagios dashboard

![image](https://user-images.githubusercontent.com/120269399/234783880-30ade2e5-0d87-402d-8a65-fd7a271258bb.png)

- [ ] 	To manually add a new host, select the Hosts link located under Monitoring on the left menu of CCM

![image](https://user-images.githubusercontent.com/120269399/234784057-74ed2331-c615-4f93-b846-34a39b6e8270.png)

This will bring up the Host Management page, which displays a list of the current hosts being monitored by Nagios XI.

![image](https://user-images.githubusercontent.com/120269399/234784277-c5f8514b-f357-4a55-b7a5-997df5b14daa.png)

- [ ] Click on Add hosts

   ![image](https://user-images.githubusercontent.com/120269399/234786131-78972d81-b028-4724-9db3-2df4bca4318b.png)
   
 - [ ] The Host Management page will open on the Common Settings tab.

![image](https://user-images.githubusercontent.com/120269399/234786291-b8d3875b-b12c-4262-958e-dc75b45a2b5f.png)

- [ ]	Define the primary host parameters such as Host Name, Description, Address, and Display name.
![image](https://user-images.githubusercontent.com/120269399/234786484-203eeafa-da30-44a2-87d2-425ab70f2f8a.png)



