Most students pick Amazon AWS as the main platform for their research. You can also choose Google Cloud or Microsoft Azure or your local testbeds, or public testbed such as [CloudLab](https://www.cloudlab.us/).
I'd encourage you to set up AWS accounts first and refer to other options as needed by your projects. 

# Amazon AWS
## Get an AWS account
First you will have to sign up for an AWS regular account, if you don’t already have one. Do not apply for an AWS Educate Starter Account. You could then apply the AWS credits received from course TFs to your regular account (see this [link](https://aws.amazon.com/awscredits/) for info about redeeming credits). Below are a few tips of using the AWS account.
- Set up a billing alert to make sure you don’t accidentally use up your free credits without noticing.
- Stop your instances when are done for the day to avoid incurring charges. Use your funds wisely.
- Terminate them when you are sure you are done with your instance (disk storage also costs something, and can be significant if you have a large disk footprint).

## Security Group
The first thing that you'll want to do after logging into your AWS account is to create a security group. These security groups control which traffic is allowed between your AWS EC2 instances, so in order to do distributed training, we'll need to allow TCP connections between instances.
1. Click into EC2 from the AWS homepage and go into **Security Groups** on the sidebar.
2. Click **Create security group**, choose a name for the group and create the security group. Select the group that you just created and under **Actions**, choose **Edit inbound rules**.
3. Now you'll need to add an inbound rule for the group to allow connections from instances within the same security group. Click **Add rule** and choose **All traffic** for the type. Click the search icon for source and scroll until you find the security group itself and then save the rule. 

## Instances
Now we can generate the actual AWS EC2 instances. We'll be using 2 relatively small CPU instance for this warm-up project, but you'll likely use GPU instances for future projects.
1. Go to **Instances** in the sidebar and click launch instances.
2. Enter a name you'd like and then scroll down and choose c4.large for the **Instance type**. This is compute instance with 2 vCPUs.
3. Under **Key pair**, create a new keypair with RSA and .pem and save it (remember this location).
4. Choose **select existing security group** and choose the security group that you made.
5. Increase the storage to 20 GiB.
6. Increase the number of instances to 2 and **Launch instance**.

## Connecting
Now that the instances are online, you can connect to them using secure shell (SSH) protocol from your terminal. Since you created two instances, I would suggest opening two different terminals to do the steps simultaneously for both instances.
1. In your instance page on AWS, click into the instance you want to connect to and copy the Public IPv4 DNS address. 
2. In your terminal, go to the directory you saved the keypair at, and run the command `chmod 400 keypair.pem` if on Linux and Mac. If running a Ubuntu subsystem or a Windows machine, use the directions [here](https://narmadanannaka.com/how-to-run-the-chmod400-command-on-windows). This changes the permissions so that only the user can read the key. Note that you will not be able to SSH into your instance if you do not properly protect the key.
3. Run the command `ssh -i keypair.pem ec2-user@[Public IPv4 DNS]` to connect to the instance.
4. Run `sudo yum update -y` and `sudo yum install git -y` to install git.

## Quota Request

Your AWS account has default quotas, but you can request a quota increase, such as access to more GPU instances, through one of following options. Increases are not granted immediately. It might take a couple of days for your increase to take effect.

- Open the [Service Quotas console](https://console.aws.amazon.com/servicequotas/home). In the navigation pane, choose **AWS services**. Select a service, select a quota, and follow the directions to [request a quota increase](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html).
- Use the [request-service-quota-increase](https://docs.aws.amazon.com/cli/latest/reference/service-quotas/request-service-quota-increase.html) AWS CLI command.
If a service is not yet available in Service Quotas, create a [service limit increase case](https://support.console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase) using the AWS Support Center Console.

# Google Cloud

# Microsoft Azure
