# 🚀 Introduction to Amazon EC2

## 📖 Overview

In this lab, I learned the fundamentals of Amazon Elastic Compute Cloud (Amazon EC2). I launched my first virtual server in AWS, monitored its performance, updated its security settings to host a simple web application, resized the instance to meet changing resource requirements, and tested termination protection before safely deleting the instance.

This lab gave me practical experience with managing compute resources in AWS and helped me understand the basic lifecycle of an Amazon EC2 instance.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Launch an Amazon EC2 instance with termination protection enabled.
- Monitor the health and performance of an EC2 instance.
- Configure a security group to allow HTTP traffic.
- Deploy and access a simple web server.
- Resize an EC2 instance and its attached Amazon EBS volume.
- Test and disable termination protection.
- Safely terminate an EC2 instance.

---

## 🛠️ AWS Services Used

- Amazon EC2
- Amazon Elastic Block Store (Amazon EBS)
- Amazon CloudWatch
- Amazon VPC
- Security Groups

---

# Task 1 – Launching an Amazon EC2 Instance

I started by opening the **Amazon EC2 Console** from the AWS Management Console and launched a new EC2 instance.

During the launch process, I configured the following settings:

| Setting | Value |
|----------|-------|
| Instance Name | Web Server |
| AMI | Amazon Linux 2023 |
| Instance Type | t3.micro |
| Key Pair | Proceed without a key pair |
| VPC | Lab VPC |
| Security Group | Web Server security group |
| Storage | 8 GiB Amazon EBS |

To improve security, I removed the default SSH rule because remote login was not required for this lab.

Before launching the instance, I enabled **Termination Protection** to prevent accidental deletion.

I also configured a **User Data** script to automatically install and start the Apache web server whenever the instance launched.

### User Data Script

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

After reviewing my configuration, I launched the instance and confirmed that it successfully entered the **Running** state with both status checks passing.

---

# Task 2 – Monitoring My EC2 Instance

After launching the instance, I explored several monitoring features provided by Amazon EC2.

I reviewed the **Status Checks** tab and confirmed that both the **System Reachability** and **Instance Reachability** checks had passed successfully.

Next, I opened the **Monitoring** tab to view the Amazon CloudWatch metrics that AWS automatically collects for EC2 instances.

Although the instance had only recently launched, I was able to review the available performance graphs.

I also explored the **Get Instance Screenshot** feature, which captures the console output of the virtual machine. This is useful for troubleshooting when an instance cannot be accessed remotely.

---

# Task 3 – Updating the Security Group and Accessing the Web Server

Once the instance was running, I copied its public IPv4 address and attempted to open the hosted website in my browser.

Initially, the page did not load because the security group was blocking inbound HTTP traffic.

To resolve this, I updated the inbound rules of the security group.

| Rule | Configuration |
|------|---------------|
| Type | HTTP |
| Port | 80 |
| Source | Anywhere (IPv4) |

After saving the rule, I refreshed the browser and successfully accessed the web server.

The page displayed the following message:

```text
Hello From Your Web Server!
```

This task helped me understand how AWS Security Groups act as virtual firewalls that control network traffic.

---

# Task 4 – Resizing My EC2 Instance

To learn how AWS supports scalable infrastructure, I resized both the EC2 instance and its attached storage.

First, I safely stopped the instance.

I then changed the instance type:

| Before | After |
|---------|-------|
| t3.micro | t3.small |

Next, I modified the attached Amazon EBS root volume.

| Before | After |
|---------|-------|
| 8 GiB | 10 GiB |

After saving the changes, I restarted the instance and verified that it launched successfully with the updated resources.

This demonstrated how cloud infrastructure can easily scale as application requirements change.

---

# Task 5 – Testing Termination Protection

In the final task, I tested Amazon EC2's termination protection feature.

First, I attempted to terminate the instance while termination protection was still enabled.

AWS prevented the deletion and displayed an error indicating that the instance could not be terminated.

I then disabled termination protection from the instance settings and repeated the termination process.

This time, the instance terminated successfully.

This exercise demonstrated how termination protection helps prevent accidental deletion of important cloud resources.

---

# 💡 Skills Demonstrated

Throughout this lab, I gained hands-on experience with:

- Launching Amazon EC2 instances
- Configuring Security Groups
- Managing Amazon VPC networking
- Deploying an Apache Web Server using User Data
- Monitoring EC2 instances with Amazon CloudWatch
- Scaling EC2 compute resources
- Resizing Amazon EBS storage
- Implementing termination protection
- Managing the complete EC2 instance lifecycle

---

# 📚 Key Takeaways

This lab introduced me to the core concepts of Amazon EC2 and cloud infrastructure management.

I learned how to deploy, monitor, secure, resize, and terminate virtual servers in AWS while gaining practical experience with several AWS services that are widely used in production environments.

Completing this lab strengthened my understanding of Infrastructure as a Service (IaaS) and provided a solid foundation for future AWS projects.

---

## 📁 Repository Structure

```
aws-ec2-introduction/
│
├── README.md
└── images/
    ├── launch-instance.png
    ├── ec2-running.png
    ├── security-group.png
    ├── web-server.png
    └── resize-instance.png
```
