# 3-tier-architecture-aws

![aws-3-tier](https://github.com/gajjarmeshw/3-tier-architecture-aws/blob/main/aws-3-tier.png)

## Architecture

This network architecture has three subnet tiers split across three availability zones. The web subnets also have a VPC routing table that will provide it access to the internet. The application and database tiers will not have such access; their routing tables will only allow internal network communication.

## Steps
### 1. Set up the VPC:

- Go to the AWS Management Console and navigate to the VPC service.

- Create a new VPC and specify the IP range for your VPC.

- Create subnets within the VPC, specifying the IP ranges for each subnet.

- Create an internet gateway and attach it to the VPC.

- Configure route tables to route traffic between subnets and the internet.

### 2. Launch EC2 instances within the VPC:

- Go to the EC2 service in the AWS Management Console.

- Launch EC2 instances, selecting the desired instance type, AMI (Amazon Machine Image), and VPC settings.


- Choose the appropriate subnet for each EC2 instance.

- Configure security groups to control inbound and outbound traffic to the EC2 instances.

- Launch and set up the EC2 instances with the required software and applications.

### 3. Set up the RDS database:

- Go to the RDS service in the AWS Management Console.
- Select the desired database engine (e.g., MySQL, PostgreSQL, etc.).

- Choose the specifications for your database instance, such as instance type, storage, and multi-AZ deployment for high availability.

- Configure the database settings, including the database name, username, and password.

- Select the VPC and subnets where you want to deploy the RDS instance.

- Configure security groups to control access to the RDS instance, allowing traffic from the EC2 instances if necessary.

- Launch the RDS instance and wait for it to be available.

- Connect EC2 instances to the RDS database:

- Obtain the endpoint or DNS name of the RDS instance from the RDS console.

- Configure the EC2 instances to connect to the RDS database using the appropriate database driver or client library.

Use the endpoint, username, and password configured for the RDS instance to establish the connection from the EC2 instances.
