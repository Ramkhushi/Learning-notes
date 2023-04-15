**Date** 16th April
### Tasks
- [ ] Create first jenkins jobs

![image](https://user-images.githubusercontent.com/120269399/232205784-11d12844-8e80-4284-ba5d-646c7186d9df.png)
![image](https://user-images.githubusercontent.com/120269399/232205810-23a7e356-8e47-4302-ae28-0d1ca18c8ee3.png)
**move to build and select execute shell if you want to run linux command.**
![image](https://user-images.githubusercontent.com/120269399/232205895-b56405c9-c2e7-4733-999c-bbd2ceec54a1.png)
** you can write command like ls,whoami etc**
 
 **save and apply**
 ![image](https://user-images.githubusercontent.com/120269399/232206054-46646d2a-b069-4137-be2b-cf56f4f1501e.png)
![image](https://user-images.githubusercontent.com/120269399/232206064-3421c145-1922-4e06-b726-8cabf2ce3a3c.png)
![image](https://user-images.githubusercontent.com/120269399/232206082-c02d2266-2f1f-4dac-a84a-21c7261b7512.png)
![image](https://user-images.githubusercontent.com/120269399/232206091-d3718248-f580-48ec-85c2-39ebcf1e5297.png)


- [ ] Create a war file using jenkins

- Login to your jenkins Server 
**then** Select free style and click on Ok
![image](https://user-images.githubusercontent.com/120269399/232208021-9ac105b8-d593-4374-9e33-234046bd6b56.png)
**Select Source Code Management**
![image](https://user-images.githubusercontent.com/120269399/232208080-59a4688a-7a6f-4ad1-8dec-8984c710124e.png)
**click on Git** and provide repo url
![image](https://user-images.githubusercontent.com/120269399/232208122-4602ef01-0506-41d0-9212-f6a1624ef62c.png)
![image](https://user-images.githubusercontent.com/120269399/232208218-85d243d5-2464-4b31-b548-641c65bfe8e3.png)
**Now got to build step** and select maven target
![image](https://user-images.githubusercontent.com/120269399/232208318-584936b3-ee0f-4f03-98f5-509d6f9e1fd7.png)
![image](https://user-images.githubusercontent.com/120269399/232208337-7b396904-6c9b-4ec4-96cb-675ce996f015.png)
**Save and apply** click on build now
![image](https://user-images.githubusercontent.com/120269399/232208383-b9a6833d-3e22-4aea-8f5b-94549abcc727.png)
**in Workspce you can check your war file created**
![image](https://user-images.githubusercontent.com/120269399/232208421-7aa2eec2-7905-4dfc-ba86-82d0850680cb.png)

- [ ] Set up build trigger

**Go to build trigger and select build periodically**
![image](https://user-images.githubusercontent.com/120269399/232208469-5d896212-9c6f-46f4-871e-0459bfb95341.png)
**Modify any schedule as per your need**
![image](https://user-images.githubusercontent.com/120269399/232208513-cbeb114d-a194-4f94-976a-37348649c15b.png)
**This will trigger after every 15 mins**
![image](https://user-images.githubusercontent.com/120269399/232208540-40b5e929-a5fb-4745-96e1-ccb79b5f1d6d.png)
**Same for SCM poll**
![image](https://user-images.githubusercontent.com/120269399/232208660-9ad1efa5-5684-4243-a72e-72395f38ad22.png)




- [ ] Test Environment variable for Jenkins 

**To access Jenkins Environemenr variable Please go to Build steps and select Execute shell**
![image](https://user-images.githubusercontent.com/120269399/232208741-370b66ad-63c2-4aec-b2cb-f0c8e181b47e.png)
** Click on See the list of available environment variables**
![image](https://user-images.githubusercontent.com/120269399/232209019-9a438b2f-c1d0-4c4d-a6cf-e7ba189839f2.png)

**Test any environment varaible**
![image](https://user-images.githubusercontent.com/120269399/232209688-03f7fb0d-6e0c-4339-91b8-29c9781d3959.png)


- [ ] Deploy war file to tomcat server 

**will be updated after docker Class**
- [ ] Make a test
**will be updated after docker Class**
