- [ ] Open the vscode 
- [ ] create a file provider.tf

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "4.64.0"
    }
  }
}

provider "aws" {
  region     = "us-east-1"
  access_key = "copy from your aws account "
  secret_key = "copy from your aws account"
  token = "<copy from your aws account>"
}
```
- [ ] run the below command

```
terraform init
```

- [ ] Create another file

```
resource "aws_instance" "web" {
  ami           = "ami-02396cdd13e9a1257"
  instance_type = "t2.micro"

  tags = {
    Name = "HelloWorld"
  }
}
```


- [ ] Run the below command to check what your code will do

```
terraform plan
```

- [ ] Execute your code to create vm

```
terraform apply
```
- [ ] Create a key with name test

- [ ] Code for key

```
resource "aws_instance" "web" {
  ami           = "ami-007855ac798b5175e"
  instance_type = "t2.micro"
  key_name =  "test"

  tags = {
    Name = "HelloWorld"
  }
}
```

- [ ] Now try to login

```
ssh -i <pemfile> ubuntu@ip
```





