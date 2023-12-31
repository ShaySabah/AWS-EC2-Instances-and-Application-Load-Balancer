# AWS EC2 Instances and Application Load Balancer Walkthrough

In this walkthrough, we will take you through the process of setting up two new Linux EC2 instances to be used as web servers and creating an Application Load Balancer (ALB) to balance traffic between these instances. We'll also simulate an unhealthy instance to show how load balancing behaves in response.

## Overview

- **Overviewing the Resources**: We'll start by understanding the AWS resources we'll be building and how they work together.
- **Creating EC2 Instances**: We'll create two new Linux EC2 instances that will serve as our web servers.
- **Creating an Application Load Balancer**: Next, we'll set up an Application Load Balancer in AWS.
- **Creating a Target Group**: We'll create a Target Group for the Load Balancer to route traffic to our EC2 instances.
- **Testing the Load Balancer**: We'll ensure the Load Balancer is working correctly by testing it.
- **Simulating an Unhealthy Instance**: Finally, we'll simulate an unhealthy instance to observe how Load Balancing responds.

![image](https://github.com/ShaySabah/AWS-EC2-Instances-and-Application-Load-Balancer/assets/139687184/856f454f-1d9f-4b22-8c3e-b32a4bbcca3b)


Let's get started.

## Creating EC2 Instances

1. **Launch EC2 Instances**: In your AWS Management Console, navigate to EC2. Launch two new Amazon Linux 2 EC2 instances in your desired region. Make sure to select the instance type that suits your needs.

2. **Key Pair**: During instance creation, specify an SSH key pair that you'll use to access the instances. Take note of the instance IDs, public IP addresses, or DNS names.

## Creating an Application Load Balancer

1. **Navigate to EC2**: Go back to your AWS Management Console and access the EC2 Dashboard.

2. **Create an ALB**: Under "Load Balancers," create a new Application Load Balancer (ALB).

3. **Configuration**: Configure the ALB with appropriate listeners and availability zones to route incoming traffic effectively.

4. **VPC and Subnets**: Ensure that the ALB is associated with your Virtual Private Cloud (VPC) and the desired subnets.

## Creating a Target Group

1. **Target Group Creation**: In the ALB configuration, create a new Target Group.

2. **Target Type**: Specify the target type as "Instance."

3. **Instance Registration**: Register the EC2 instances you created earlier with this Target Group.

## Testing the Load Balancer

1. **Access the ALB**: Access the DNS name or public DNS of your ALB, and you should see the web content served by one of the EC2 instances.

2. **Traffic Distribution**: Refresh the page multiple times to observe how the ALB efficiently distributes traffic between the two instances.

## Simulating an Unhealthy Instance

1. **Identify an Instance**: In the EC2 Dashboard, identify one of your EC2 instances that you'd like to simulate as unhealthy.

2. **Stop or Terminate**: Temporarily stop or terminate the selected instance.

3. **Observe Load Balancing**: Observe how the ALB automatically routes traffic to the healthy instance, demonstrating the resiliency of the load balancing setup.

That concludes our walkthrough. You've successfully set up Linux EC2 instances as web servers, created an Application Load Balancer, and configured a Target Group for load balancing. By simulating an unhealthy instance, you've also witnessed how load balancing reacts to failures. This hands-on experience provides insights into managing scalable and reliable applications on AWS.
