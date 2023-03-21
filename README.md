# AwsCli Setup Labs
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

For consistency and quick access, let set the region to `eu-central-1`.

### Switch Role

After the account has been created, you will receive the account ID and the appropriate role to switch into to access resources on your account.

On the top right of the console, click on your Username to show the drop-down menu and click on `Switch Roles`. Fill in the necessary information

```
Provided for Cloudreach AWS Vending Machine by email

Account: <account_id> provided for Cloudreach AWS Vending Machine by email
Role: LabUserAdmin
Display Name: LabUserAdmin
```

### Create a new user for programmatical access for AWS Identity and Access Management (IAM)
>AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. 
>With IAM, you can centrally manage permissions that control which AWS resources users can access. 
>You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.

* Go to AWS IAM > User Groups
* Click on `Create group`
* Set the user group name
* Scroll down and Attach permissions policies 
* Search for the policy name `AdministratorAccess` Type `AWS managed - job function` select the box, then click on `Create group`
* Go to AWS IAM > Users
* Click on `Add users`
* Set your user name then click on `Next`
* For `Set Permissions`, select the `Add user to group`
* Search for `User groups` and check `Administrator`the selection box, then click on `Next`
* Set Tags tags then click on `Add new tag`
* Enter Key=Name Value=<yourname> e.g. Value=Will Smith
* then click on `Add new tag`
* Enter Key=Company Value=<yourcompany> e.g. Value=Cloudreach
* then click on `Add new tag`
* Enter Key=Profile Value=<yourjobprofile> e.g. Value=Cloud Systems Developer
* then click on `Add new tag`
* Enter Key=Location Value=<yourlocation> e.g. Value=Germany
* Review the details and click on `Create user`
* Go to AWS IAM > Users
* Click on your user name then press `Security credential Tab`
* Scroll down and press `Create access keys`
* Select Command Line Interface (CLI) selection box
* Select the box with `I understand the above recommendation and want to proceed to create an access key.`
* No Tag is necesary then click on `Create access key`

> You should now have the `access_key` and `secret_access_key` displayed.
> This is the only time that the secret access key can be viewed or downloaded. 
> You cannot recover it later. However, you can create a new access key any time.

Access key best practices
* Never store your access key in plain text, in a code repository, or in code.
* Disable or delete access key when no longer needed.
* Enable least-privilege permissions.
* Rotate access keys regularly.
* For more details about managing access keys, see the [Best practices for managing AWS access keys](https://docs.aws.amazon.com/console/general/access-keys-best-practices)

### AWS config & credentials

Check that the folder `~/.aws` exists and create it if it does not. Open or create a new file in `~/.aws/config`. The config file contains the AWS account configurations for each user/role you will need to access an account.

```
vi ~/.aws/config
```

Add the lines:
```
[Cloudreach]
region = eu-west-1
account = 123456789
profile = talent-academy
role = LabUserAdmin
output = json
```

Open or create a new file in `~/.aws/credentials`. This is where you will save both the ACCESS and SECRET key to your account with a profile name.

```
vi ~/.aws/credentials
```

```
[talent-academy]
aws_access_key_id = <ACCESS_KEY>
aws_secret_access_key = <SECRET_ACCESS_KEY>
```

### Export the required profile

The aws cli requires you to specify which configuration profile you wish to use everytime you execute the command. Instead of typing the profile name each time, you can expose it in the `Environment Variable` of your current terminal session by typing this command:

```
export AWS_PROFILE="talent-academy"
export AWS_DEFAULT_REGION="eu-west-1"
```

Now each time the cli is ran, both variables will be used as paramters to the command to access the right configuration.

### Test your access

Run the following command to check that your access and configuration are working:

```
aws iam list-users
```
