# 🔥Amazon Web Services(AWS)

<img src="./assets/images/aws.png" alt="AWS" width="700">

> **Amazon Web Services (AWS)** is a subsidiary of Amazon that provides on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered pay-as-you-go basis.

> AWS is the market leader in **Iaas** and **Paas**.

### ✳IAM(Identity Access Management)

<img src="./assets/images/iam.png" alt="IAM" width="200">

?> **AWS Identity and Access Management (IAM)** enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources.

?> It is similar to [Okta](https://www.okta.com/)

[🌐 AWS Documentation](https://aws.amazon.com/iam/)

### ✳EC2(Elastic Compute Cloud)

<img src="./assets/images/ec2.png" alt="EC2" width="500">

?> **Amazon Elastic Compute Cloud (Amazon EC2)** is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.

?> It is similar to [DigitalOcean Droplets](https://www.digitalocean.com/products/droplets/)

[🌐 AWS Documentation](https://aws.amazon.com/ec2/)
[🌐 AWS S3 - All You Need To Know About This Service](https://catalins.tech/aws-s3-all-you-need-to-know-about-this-service)

### ✳S3(Simple Storage Service)

<img src="./assets/images/s3.png" alt="s3" width="500">

?> **Amazon Simple Storage Service (Amazon S3)** is an object storage service that offers industry-leading scalability, data availability, security, and performance. This means customers of all sizes and industries can use it to store and protect any amount of data for a range of use cases, such as websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics.

?> It is similar to [DigitalOcean Spaces](https://www.digitalocean.com/products/spaces/)
[🌐 AWS Documentation](https://aws.amazon.com/s3/)

### ✳Lambda

<img src="./assets/images/lambda.png" alt="lambda" height="200" width="200">

?> **AWS Lambda** lets you run code without provisioning or managing servers. You pay only for the compute time you consume.

In order to deploy our applications using Lambda, we use [Serverless](https://github.com/serverless/serverless) package to directly deploy our applications into AWS Lambda.

1. We should create user using **AWS IAM**.
2. We should configure above user credentials in serverless package. So that you can deploy your application in AWS Lambda.

?> It is similar to [Netlify Functions](https://www.netlify.com/products/functions/)

[🌐 AWS Documentation](https://aws.amazon.com/lambda/)

### ✳Cloud Front

<img src="./assets/images/cloud_front.png" alt="cloud front" width="300">

?> **Amazon CloudFront** is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.

?> It is similar to [CLOUDFARE](https://www.cloudflare.com/)

[🌐 AWS Documentation](https://aws.amazon.com/cloudfront/)

### ✳DynamoDB

<img src="./assets/images/dynamodb.png" alt="dynamodb" width="300">

?> **Amazon DynamoDB** is a key-value and document database that delivers single-digit millisecond performance at any scale.

?> It is similar to [MongoDB](https://www.mongodb.com/)

[🌐 AWS Documentation](https://aws.amazon.com/dynamodb/)

### ✳List of AWS Services

> [Complete List of AWS Services](https://adayinthelifeof.nl/2020/05/20/aws.html)

### ✳AWS Elastic Load Balancing

<img src="./assets/images/load-balancer.png" alt="load balancer" width="300">

?> **Elastic Load Balancing** automatically distributes traffic across multiple targets – Amazon EC2 instances, containers and IP addresses – in a single Availability Zone or multiple Availability Zones. Elastic Load Balancing can detect unhealthy targets, stop sending traffic to them, and then spread the load across the remaining healthy targets.

?> You can select the appropriate load balancer based on your application needs.

Elastic Load Balancing supports three types of load balancers:

1. [Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
2. [Network Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)
3. [Classic Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/introduction.html)

**Classic Load Balancer**

<img src="./assets/images/classic.png" alt="load balancer" width="300">

?> A load balancer distributes incoming application traffic across multiple EC2 instances in multiple Availability Zones. This increases the fault tolerance of your applications

**Application Load Balancers**

<img src="./assets/images/application.png" alt="load balancer" width="300">

?> An Application Load Balancer **functions at the application layer**, the seventh layer of the Open Systems Interconnection (OSI) model. After the load balancer receives a request, it evaluates the listener rules in priority order to determine which rule to apply, and then selects a target from the target group for the rule action. You can configure listener rules to route requests to different target groups based on the content of the application traffic. Routing is performed independently for each target group, even when a target is registered with multiple target groups. You can configure the routing algorithm used at the target group level. The default routing algorithm is round robin; alternatively, you can specify the least outstanding requests routing algorithm.

**Network Load Balancers**

?> A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to **open a TCP connection to the selected target** on the port specified in the listener configuration.



### ✳AWS Flow

> We can use Amazon web services according to our business model. Following one is one of the examples:

<img src="./assets/images/aws_flow.png" alt="aws flow" width="700">

### ⚡Test AWS Services Offline

<img src="./assets/images/localstack.png" alt="localstack" width="300">

?> **LocalStack** provides an easy-to-use test/mocking framework for developing Cloud applications. It spins up a testing environment on your local machine that provides the same functionality and APIs as the real AWS cloud environment.

> [🌐 LocalStack](https://localstack.cloud/)
