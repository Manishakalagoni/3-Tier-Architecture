# 3-Tier-Architecture
**Highly Available 3-Tier Web Application on AWS**

This architecture utilizes a three-tier model for deploying a web application across multiple environments (Dev, Perf, QA, Prod).

**Presentation Tier:** An Application Load Balancer (ALB) distributes incoming traffic across EC2 instances running the web application. This tier can leverage features like SSL termination for improved security.

**Application Tier:** This layer consists of an Auto Scaling Group (ASG) that manages a pool of EC2 instances hosting the web application code. The ASG automatically scales instances based on pre-defined CloudWatch alarm metrics, ensuring high availability and performance during traffic spikes.

**Data Tier:** A managed database service like Amazon RDS provides a scalable and reliable data storage solution for the application.

**Testing and Scalability Validation**

Manual stress testing was conducted by simulating high CPU load on the web application. As expected, the ALB routed traffic to additional instances within the ASG upon triggering a CloudWatch alarm based on CPU utilization. This confirms the architecture's ability to handle increased traffic and maintain application uptime.

**Additional Considerations:**

Implement security groups to restrict inbound and outbound traffic for each tier.

Integrate a CI/CD pipeline for automated deployments across environments.

Utilize additional AWS services like CloudWatch Logs for application and infrastructure monitoring

![image](https://github.com/Manishakalagoni/3-Tier-Architecture/assets/114309498/37cf5110-2e20-4d8e-ac30-126fb075760a)

