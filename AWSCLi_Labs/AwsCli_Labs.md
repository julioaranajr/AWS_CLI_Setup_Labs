# AWS LABS

```
aws --version
```

```
export AWS_PROFILE="cloudreach-ta-lab"
export AWS_DEFAULT_REGION="eu-west-1"
```

```
[cloudreach-ta-lab]
region = eu-west-1
user = my.user.name@domain.name
account = 123456789
profile = cloudreach-ta-lab
role = LabUserAdmin
output = json
```
![Screenshot](https://github.com/julioaranajr/02_AwsCli_Setup_Labs/blob/main/AWSCLi_Labs/Screenshot%202022-09-30-aws-labs.png)

```
[cloudreach-ta-lab]
aws_access_key_id = <ACCESS_KEY>
aws_secret_access_key = <SECRET_ACCESS_KEY>
```
```
aws iam list-users
```
![Screenshot](https://github.com/julioaranajr/02_AwsCli_Setup_Labs/blob/main/AWSCLi_Labs/Screenshot%202022-09-30-iam-users.png)