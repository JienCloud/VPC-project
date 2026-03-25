# Build a Virtual Private Cloud

**Author:** Jieno Renz Cadiz  
**Email:** jienorenzcadiz@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/contented_white_innocent_cobra/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create an Amazon VPC, Public subent, and internet gateway. I'm doing this project to learn gain hands-on experience about Amazon VPC.

### What is Amazon VPC?

Amazon VPC is If we imagine your AWS Region as a country, a Virtual Private Cloud (VPC) is like your own private city inside that country.

You can design neighborhoods (known as subnets, which you'll learn about in this project), traffic rules, and security measures to control how resources, like EC2 instances and databases, connect and work together.

It is useful because you can create your own private and public city to share or just keep it within your own city the data of your services like instances.

In today's project, I used Amazon VPC to create a VPC, create Subnets, and create an internet gateway. In addition I used CloudShell so instead of clicking i used code to quickly create vpc, subnets, and internet gateway.

### Personal reflection

This project took me about 1-2 hours since I am a Computer Engineering student who learned a bit about networking like IP addresses.

One thing I didn't expect in this project was I can use code instead of just clicking. After doing recent projects of S3 buckets, EC2, and IAM. I used just clicking but now I learned I can also use code if I wanted to.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will access the VPC console in AWS  and create a VPC. because I want to explore and do hands-on project using the Amazon VPC.

### How VPCs work

VPCs are the reason why resources can be made private to you. You also get control over resources in a VPC, so you can organize how they communicate and integrate with each other without the public internet.

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because of VPC, this service lets us launch resources like instances. This also let us connect services.

![Image](http://learn.nextwork.org/contented_white_innocent_cobra/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is a ranged of IP addresses that my VPC can allocate to the resources doployed into my VPC.

---

## Subnets

### What I did in this step

In this step, I will launch a subnet inside my VPC.

### Creating and configuring subnets

Subnets are subnets are like different neighborhoods inside your city. You use subnets to group resources with similar access rules and restrictions. Some subnets might be public areas that all resources can access (public subnets) while others are private areas with limited access (private subnets). A VPC can have as many public and private subnets as you need, but subnets in the same VPC cannot have overlapping IP address CIDR blocks! This means each subnet must have a unique range of IP addresses. The default VPC in your account comes with predefined subnets in each Availability Zone of a Region, which means you'll see 3 subnets on your page if your Region has 3 Availability Zones.

### Public vs private subnets

The difference between public and private subnets are A public subnet is connected to the internet. Resources inside a public subnet can communicate with external networks.

A private subnet does not have direct internet access. You'd use it for internal resources that don’t need to be publicly accessible.

For a subnet to be considered public, it has to connect to an internet gateway to call it public.

![Image](http://learn.nextwork.org/contented_white_innocent_cobra/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 address. When you enable auto-assign public IPv4 address for a subnet, any EC2 instance launched in that subnet will instantly get a public IP address so you won't have to create one manually - a huge time saver.

---

## Internet gateways

### What I did in this step

In this step, I will connect your VPC to the internet using a internet gateway. because I want other's data to enter and exit my VPC. 

### Setting up internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

An internet gateway connects your city (VPC) and the outside world (internet).


Attaching an internet gateway to a VPC means resources in your VPC can now access the internet. The EC2 instances with public IP addresses also become accessible to users, so your applications hosted on those servers become public too. If I missed this step then the EC2 instances will always be private and cannot be accessed by the internet.

![Image](http://learn.nextwork.org/contented_white_innocent_cobra/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will Open a handy tool (called AWS CloudShell) to run commands, run AWS CLI commands to set up a VPC, subnet and internet gateway. because this will be addition to my project of creating a VPC, Subnets, and Internet gateway. 

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is shell in your AWS Management Console, which means it's a space for you to run code. The awesome thing about AWS CloudShell is that it already has AWS CLI pre-installed. CLI is.

### Debugging my setup

To set up a VPC or a subnet, you can use the command 
To create vpc:
     aws ec2 create-tags --resources=vpc-ID --tags Key=Name,Value="VPC name"
vpc ID= your VPC ID

To create a subnet:
aws ec2 create-subnet --vpc-id vpc-123bhuiyof78

 Make sure to avoid errors like missing parameters this should be solve by including --cidr-block which defines a subnet's CIDR block range. Without this, the CLI cannot create the subnet because it doesn’t know which IP addresses to allocate for it.

![Image](http://learn.nextwork.org/contented_white_innocent_cobra/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is you don't neet to click to do a task but  use codes to quickly do tasks. An advantage of using the Console is to do the tasks more efficiently. Overall, I preferred both of them as of now but I would like to use the CloudShell more often in the future after having deep knowledge about cloud.

---

---
