# 02_AwsCli_Setup_Labs
Repository to Setup AWS CLI and Exsercies

# AWS Lab


Go to [Cloudreach AWS Vending Machine](https://aws.vending-machine.cloudreach.io/home/welcome) to request a Personal Development Lab.
This should take a few minutes for the request to be process and receive an email with your access details.

### Set up AWS CLI on your mac

```
brew install awscli
```

Test that awscli is working:

```
aws --version
```

### Access AWS Lab Account

Labs can be access from the [Cloudreach OneLogin Portal](https://cloudreach.onelogin.com) and click on the `AWS Lab` icon.

### Region

For consistency and quick access, let set the region to `eu-west-1`.

### Switch Role

After the account has been created, you will receive the account ID and the appropriate role to switch into to access resources on your account.

On the top right of the console, click on your Username to show the drop-down menu and click on `Switch Roles`. Fill in the necessary information

```
Account: <account_id>
Role: LabUserAdmin
Display Name: LabUserAdmin
```

### Create a new user for programmatical access

* Go to AWS IAM > Users
* Click on `Add users`
* Set your user name
* For the `AWS credential type` check the `Access key - Programmatic access` box, then click on `Next`
* For `Set Permissions`, select the `Attach existing policies directly`
* Search for `AdministratorAccess` and check the selection box, then click on `Next: Tags`
* No tags is needed, so proceed with `Next: Review`
* Review the details and click on `Create user`

You should now have the `access_key` and `secret_access_key` displayed.

### AWS config & credentials

Check that the folder `~/.aws` exists and create it if it does not. Open or create a new file in `~/.aws/config`. The config file contains the AWS account configurations for each user/role you will need to access an account.

```
vi ~/.aws/config
```

Add the lines:
```
[cloudreach-ta-lab]
region = eu-west-1
user = your.username.named@domain.name
account = 123456789
profile = cloudreach-ta-lab
role = LabUserAdmin
output = json
```

Open or create a new file in `~/.aws/credentials`. This is where you will save both the ACCESS and SECRET key to your account with a profile name.

```
vi ~/.aws/credentials
```

```
[cloudreach-ta-lab]
aws_access_key_id = <ACCESS_KEY>
aws_secret_access_key = <SECRET_ACCESS_KEY>
```

### Export the required profile

The aws cli requires you to specify which configuration profile you wish to use everytime you execute the command. Instead of typing the profile name each time, you can expose it in the `Environment Variable` of your current terminal session by typing this command:

```
export AWS_PROFILE="cloudreach-ta-lab"
export AWS_DEFAULT_REGION="eu-west-1"
```

Now each time the cli is ran, both variables will be used as paramters to the command to access the right configuration.

### Test your access

Run the following command to check that your access and configuration are working:

```
aws iam list-users
```
