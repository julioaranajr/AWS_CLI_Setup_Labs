# AWS LABS

```
aws --version
```

```
export AWS_PROFILE="talent-academy"
export AWS_DEFAULT_REGION="eu-west-1"
```

```
[talent-academy]
region = eu-west-1
user = my.user.name@domain.name
account = 123456789
profile = talent-academy
role = LabUserAdmin
output = json
```

```
[talent-academy]
aws_access_key_id = <ACCESS_KEY>
aws_secret_access_key = <SECRET_ACCESS_KEY>
```

```
aws iam list-users | tee
```

```json
{
    "Users": [
        {
            "Path": "/",
            "UserName": "Will Smith",
            "UserId": "AIDAQZRS4IU0123456789",
            "Arn": "arn:aws:iam::059876543210:user/julioarana",
            "CreateDate": "2023-02-03T21:11:25+00:00"
        }
    ]
}
```

```
aws iam list-groups | tee
```

```json
{
    "Groups": [
        {
            "Path": "/",
            "GroupName": "Administrators",
            "GroupId": "AGPA0EG-ADMINISTRATOR",
            "Arn": "arn:aws:iam::059876543210:group/Administrators",
            "CreateDate": "2023-02-03T20:23:55+00:00"
        },
        {
            "Path": "/",
            "GroupName": "Billing",
            "GroupId": "AGPA$BILLNG$-EXAMPLE",
            "Arn": "arn:aws:iam::059876543210:group/Billing",
            "CreateDate": "2023-02-03T20:35:59+00:00"
        },
        {
            "Path": "/",
            "GroupName": "Developers",
            "GroupId": "AGPAEXAMPLE-DEVELOPER",
            "Arn": "arn:aws:iam::059876543210:group/Developers",
            "CreateDate": "2023-02-03T20:36:56+00:00"
        },
        {
            "Path": "/",
            "GroupName": "System_administrators",
            "GroupId": "AGPASYS-ADMINISTRATOR",
            "Arn": "arn:aws:iam::059876543210:group/System_administrators",
            "CreateDate": "2023-02-03T20:47:28+00:00"
        }
    ]
}
```
