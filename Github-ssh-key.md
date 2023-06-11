- [ ] Generate ssh key using below command
```
ssh-keygen -f mykey
```

- [ ]  start the ssh-agent in the background
```

 eval "$(ssh-agent -s)"
```
- [ ] Add your SSH private key to the ssh-agent
```
 ssh-add private key
 ```


- [ ]  Add the Public key to your Github repo
