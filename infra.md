Most students pick Amazon AWS as the main platform for their projects. You can also choose Google Cloud or Microsoft Azure or your local testbeds, or public testbed such as CloudLab.

# Amazon AWS
A full tutorial on starting an AWS virtual machine can be found [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html).

## Get an AWS account
First you will have to sign up for an AWS regular account, if you don’t already have one. Do not apply for an AWS Educate Starter Account. 
Please send your AWS IDs to the TFs based on our Ed announcements. You can then apply the AWS credits received from course TFs to your regular account (see this [link](https://aws.amazon.com/awscredits/) for info about redeeming credits). Below are a few tips of using the AWS account.
- Set up a billing alert to make sure you don’t accidentally use up your free credits without noticing.
- Stop your instances when are done for the day to avoid incurring charges. Use your funds wisely.
- Terminate them when you are sure you are done with your instance (disk storage also costs something, and can be significant if you have a large disk footprint).

## Quota Request
Your AWS account has default quotas, but you can request a quota increase, such as access to more GPU instances, through one of following options. Increases are not granted immediately: it might take a couple of days for your increase to take effect. (From last year's experiences, AWS could delay weeks to approve new users.)

- Open the [Service Quotas console](https://console.aws.amazon.com/servicequotas/home). In the navigation pane, choose **AWS services** and select a service to view your current quotas. You will most likely be interested in the [EC2 quotas](https://console.aws.amazon.com/servicequotas/home/services/ec2/quotas).
- You can [request a quota increase](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html) using the [request-service-quota-increase](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/service-quotas/request-service-quota-increase.html) AWS CLI command or, if a service is not yet available in the Service Quotas, [create a service limit increase case](https://support.console.aws.amazon.com/support/home#/case/create?issueType=service-limit-increase) using the AWS Support Center Console.

Here are some recommended quota increase requests from TFs if you don't know what you need for your project yet:
- All Standard (A, C, D, H, I, M, R, T, Z) Spot Instance Requests: Default limit 5 ==> 100
- All G and VT Spot Instance Requests: Default limit 0 ==> 20
- All P Spot Instance Requests: Default limit 0 ==> 20

## Security Groups
The first thing that you'll want to do after logging into your AWS account is to create a security group. These security groups control which traffic is allowed between your AWS EC2 instances, so in order to do distributed training, we'll need to allow TCP connections between instances.
1. Click into EC2 from the AWS homepage and go into **Security Groups** on the sidebar.
2. Click **Create security group**, choose a name for the group and create the security group. Select the group that you just created and under **Actions**, choose **Edit inbound rules**.
3. Now you'll need to add an inbound rule for the group to allow connections from instances within the same security group. Click **Add rule** and choose **All traffic** for the type. Click the search icon for source and scroll until you find the security group itself and then save the rule. 

## Instances
Now we can generate the actual AWS EC2 instances. We'll be using 2 relatively small CPU instance for this warm-up project, but you'll likely use GPU instances for future projects.
1. Go to **Instances** in the sidebar and click **Launch instances**.
2. Enter a name you'd like and then scroll down and choose *c4.large* for the **Instance type**. This is compute instance with 2 vCPUs.
3. Under **Key pair**, create a new keypair with RSA and `.pem` and save it (remember this location).
4. Choose **select existing security group** and choose the security group that you made.
5. Increase the storage to 20 GiB.
6. Increase the number of instances to 2 and **Launch instance**.

## Connecting
Now that the instances are online, you can connect to them using secure shell (SSH) protocol from your terminal. Since you created two instances, I would suggest opening two different terminals to do the steps simultaneously for both instances.
1. In your instance page on AWS, click into the instance you want to connect to and copy the Public IPv4 DNS address. 
2. In your terminal, go to the directory you saved the keypair at, and run the command `chmod 400 keypair.pem` if on Linux and Mac. If running a Ubuntu subsystem or a Windows machine, use the directions [here](https://narmadanannaka.com/how-to-run-the-chmod400-command-on-windows). This changes the permissions so that only the user can read the key. Note that you will not be able to SSH into your instance if you do not properly protect the key.
3. Run the command `ssh -i keypair.pem ec2-user@[Public IPv4 DNS]` to connect to the instance.
4. Run `sudo yum update -y` and `sudo yum install git -y` to install git.

# Google Cloud
A full tutorial of starting Google Cloud virtual machine can be found [here](https://cloud.google.com/compute/docs/instances/create-start-instance). Each student can get 50$ credits for Google Cloud. Please check Ed posting for details.

## Instances
1. In the Google Cloud console, go to the [**VM instances**](https://console.cloud.google.com/compute/instances) page. Select your instances and click **Continue**. Click **Create instance**.
2. Specify a Name for your VM. Select a **Machine configuration** for your VM. In the **Boot disk** section, click **Change**, and then do the following: On the **Public images** tab, choose Operating system, OS version, Boot disk type, Boot disk size; To confirm your boot disk options, click **Select**.
3. In the **Firewall** section, to permit HTTP or HTTPS traffic to the VM, select **Allow HTTP traffic** or **Allow HTTPS traffic**. When you select one of these, Compute Engine adds a network tag to your VM, which associates the firewall rule with the VM. Then, Compute Engine creates the corresponding ingress [firewall rule](https://cloud.google.com/vpc/docs/firewalls) that allows all incoming traffic on `tcp:80` (HTTP) or `tcp:443` (HTTPS).
4. To create and start the VM, click **Create**.

## Connecting
Connect to VMs using [SSH-in-Browser](https://cloud.google.com/compute/docs/ssh-in-browser) from the Google Cloud console, by doing the following:
1. In the Google Cloud console, go to the [**VM instances**](https://console.cloud.google.com/compute/instances) page.
2. In the list of virtual machine instances, click **SSH** in the row of the instance that you want to connect to.

# Microsoft Azure
A full tutorial of starting Azure virtual machine can be found [here](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu).

## Get an Azure account
If you don't have an Azure subscription, create a free [account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin. You may then sign in to the [Azure portal](https://portal.azure.com/). There should be free credits for students, which you can directly [apply](https://azure.microsoft.com/en-us/free/students/).  

## Instances
1. Enter **virtual machines** in the search and select **Virtual machines** under **Service**. In the **Virtual machines** page, select **Create** and then **Virtual machine**.
2. In the **Basics** tab, under **Project details**, make sure the correct subscription is selected and then choose to **Create new resource group**. Enter *yourResourceGroup* for the name.
3. Under **Instance details**, enter *yourVM* for the Virtual machine name, choose your **Image**, and Leave the other defaults. 
4. Under **Administrator account**, select **SSH public key**. In **Username** enter *yourUsername*. For **SSH public key source**, leave the default of **Generate new key pair** and then enter *yourKey* for the **Key pair name**.
5. Under **Inbound port rules** > **Public inbound ports**, choose **Allow selected ports** and then select **SSH (22)** and **HTTP (80)** from the drop-down.
6. Leave the remaining defaults and then select the **Review + create** button at the bottom of the page. On the **Create a virtual machine** page, you can see the details about the VM you are about to create. When you are ready, select **Create**.
7. When the **Generate new key pair** window opens, select **Download private key and create resource**. Your key file will be download as *yourKey.pem*. Make sure you know where the `.pem` file was downloaded.

## Connecting
On the page for your new VM, select the **public IP address** and copy it to your clipboard. You could then create an SSH connection with the VM.
1. If you are on a Mac or Linux machine, open a Bash prompt and set read-only permission on the .pem file using chmod 400 `~/Downloads/yourKey.pem`. If you are on a Windows machine, open a PowerShell prompt.
2. At your prompt, open an SSH connection to your virtual machine. Replace the IP address with the one from your VM, and replace the path to the `.pem` with the path to where the key file was downloaded.

# Cloud Lab
See more instructions here: https://www.cloudlab.us/