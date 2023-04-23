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
  region     = "us-west-2"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
  token = "<>"
}
```
- [ ] run the below command

```
terraform init
```

- [ ] Create another file

```
resource "aws_instance" "web" {
  ami           = <imageid>
  instance_type = "t2.micro"

  tags = {
    Name = "HelloWorld"
  }
}
```
