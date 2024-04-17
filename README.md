# Thumbnail Generator
An app in python dedicated to generate thumbnail images whenever a user uploads an image to S3 bucket. 
This app is structured entirely with AWS Cloud using these elements:
- S3 Buckets.
- IAM role.
- Policies.
- Triggers.
- Lambda function.

In this repo you will find these files:
- lambda_function.py: it contains Python code to get an image and then transform it to thumbnail.
- deployment-thumbnail-package.zip: it contains the necessary tools/libraries for correctly executing the lambda_function.py
- s3_policy.json: JSON code that generates the policy needed to give permission to enter S3 Buckets and use them as origin and final repositories of thumbnail images.
- test_event.json: JSON code to test the lambda_function.py inside AWS.

## Whats the best infrastructure choice?

### AWS Cloud
#### Cons of AWS Cloud:
- Not Using Infrastructure as Code (IaC): IaC allows you to provision and manage resources using code, which improves consistency, version control, and automation.
- Replication Complexity: While AWS provides command-line interfaces (CLI) and batch files for replication, executing each task manually can be error-prone. To simplify this process, consider using tools like Former2, which generate IaC based on existing AWS infrastructure.
- Lack of External Libraries for Automation: The absence of external libraries for automation can limit flexibility. Exploring third-party libraries or custom scripts can enhance automation capabilities.
#### Pros of AWS:
- Centralized Infrastructure Configuration: AWS allows centralized management of infrastructure configuration. This facilitates better interaction with other AWS services and tools.
- IaC Options: AWS provides multiple IaC options, including:
  - AWS CloudFormation: A declarative IaC service for provisioning and managing AWS resources.
  - AWS Serverless Application Model (AWS SAM): Simplifies serverless application deployment.
  - AWS Cloud Development Kit (AWS CDK): Allows defining infrastructure using familiar programming languages.
  - HashiCorp Terraform and Pulumi: Third-party tools for managing infrastructure as code.

### IaC like Terraform or CDK
#### Pros:
- Automation and Flexibility: Terraform and CDK automate infrastructure provisioning and deployment. They offer flexibility and reproducibility.
- Scalability: These tools make it easier to scale resources as needed.
- Enhanced Security: Testing code before production deployment improves security.
#### Cons:
- Learning Curve: Learning the language and maintaining IaC can be time-consuming.
- Feedback Delay: Immediate feedback on errors may be limited compared to DevOps practices.

## Best Case Scenario:
Considering business needs and budget, a combination of traditional infrastructure management (using GUI) and IaC is recommended. AWS offers various options to explore this hybrid approach.
Remember that choosing the right approach depends on specific project requirements and organizational context. Evaluating trade-offs and aligning with business goals will guide your decision-making process. 



### Info on this topic:
- https://www.reddit.com/r/aws/comments/vk81kt/am_i_alone_in_just_using_aws_console_instead_of/
- https://www.reddit.com/r/aws/comments/11ocnwr/cloud_formation_or_terraform/
- https://docs.aws.amazon.com/prescriptive-guidance/latest/choose-iac-tool/introduction.html
- https://thenewstack.io/the-pros-and-cons-of-iac-what-you-need-

