# LLM and tutorial declaration

This file records every LLM prompt and tutorial used in this lab,
as required by Part A.2 of the assignment brief.

## Tool: Claude (Anthropic)

Claude was used as an assistant in one continuous conversation. As well as answering the
prompts below, it produced the initial code for both templates, the Python API and the
GitHub Actions workflow, checked my pushed files with cfn-lint and local tests before I
deployed them, and drafted the README. I made every commit and pull request myself,
deployed every stack, ran every test and captured every screenshot.

| Date       | Prompt                                                                 | What I used it for                                                        |
|------------|------------------------------------------------------------------------|---------------------------------------------------------------------------|
| 2026-10-10 | Asked for help with the CloudFormation Lab and shared the brief         | Overall plan, branch structure and README outline                         |
| 2026-10-10 | Asked what to name the GitHub repo and what to put in the description  | Repo name and description                                                 |
| 2026-10-10 | Asked how to set up the repo in VS Code Insiders                       | Clone steps, first commit, .gitignore                                     |
| 2026-10-10 | Asked about the line ending warning and the first commit message       | Amending the commit and pushing main                                      |
| 2026-10-10 | Asked what to write in the first pull request description              | What and Why layout for pull requests                                     |
| 2026-10-10 | Said I would use my own AWS account                                    | Account setup advice: no root user, budget alert, local tools             |
| 2026-10-10 | Asked for the basic static website template                            | `static-site/template.yaml` version 1                                     |
| 2026-10-25 | Asked whether the plan follows the brief and the Lambda IaC page        | Checked the plan against the brief                                        |
| 2026-10-25 | Asked how to set up Git on a new computer                              | Git identity and commit email                                             |
| 2026-10-25 | Asked how to fix a misplaced index.html and the missing template       | Folder layout fix                                                         |
| 2026-10-25 | Asked how to install the AWS CLI on Windows                            | AWS CLI install script                                                    |
| 2026-10-25 | Asked about the `aws login` region error                               | Region fix; I then chose to deploy through the console                    |
| 2026-10-25 | Asked how to deploy the template in the CloudFormation console         | Create stack steps and tags                                               |
| 2026-10-25 | Asked how to upload the page to S3 and test the site                   | Upload and test steps                                                     |
| 2026-10-25 | Asked what to write in pull requests and merge commits                 | Pull request and merge commit wording                                     |
| 2026-10-25 | Asked for an improved template with CloudFront and a private bucket    | Static site version 2: CloudFront, OAC, encryption, versioning            |
| 2026-10-25 | Asked how to update the stack with a change set and test it            | Change set review, HTTPS and access tests                                 |
| 2026-10-25 | Asked for a version where a Lambda function writes the page            | Static site version 3: parameters, Lambda custom resource, IAM role       |
| 2026-10-25 | Asked how to deploy and test the Lambda version                        | IAM acknowledgement, versioning and parameter validation tests            |
| 2026-10-25 | Asked for a plan for the three tier architecture                       | Design, cost estimate and branch plan                                     |
| 2026-10-25 | Asked whether the three tier part belongs to the CloudFormation Lab    | Mapped each part of the brief to the repo folders                         |
| 2026-10-25 | Asked for the three tier network template                              | VPC, subnets, NAT gateway, route tables, S3 endpoint                      |
| 2026-10-25 | Asked how to deploy and check the network stack                        | Create stack steps and resource map check                                 |
| 2026-10-25 | Asked how much of the assignment was left                              | Progress check against the brief                                          |
| 2026-10-25 | Asked whether to delete AWS resources overnight                        | Deleted the three tier stack to avoid NAT gateway charges                 |
| 2026-10-26 | Asked for the web tier template                                        | Load balancer, Auto Scaling, launch template, cfn-signal                  |
| 2026-10-26 | Asked how to deploy and test the web tier                              | Load balancing, public IP and self healing tests                          |
| 2026-10-26 | Asked whether to keep the stack running or delete it between steps     | Kept it running to add the app tier as a change set                       |
| 2026-10-26 | Asked for the application tier template                                | Internal load balancer, Python API, web to app proxy                      |
| 2026-10-26 | Asked how to deploy and test the application tier                      | Rolling update, API and internal access tests                             |
| 2026-10-26 | Asked for the database tier template                                   | RDS MySQL 8.4, password in Secrets Manager, TLS from the app              |
| 2026-10-26 | Asked how to deploy and test the database tier                         | Visit counter, RDS settings, security group and secret checks             |
| 2026-10-26 | Asked for a GitHub Actions workflow to lint the templates              | `.github/workflows/cfn-lint.yml`                                          |
| 2026-10-26 | Asked how to fix a wrong commit message and read the pull request checks | `git commit --amend`, `--force-with-lease`, deliberate failure test     |
| 2026-10-26 | Asked about adding my lecturer as a collaborator and repo visibility   | Collaborator invite                                                       |
| 2026-10-26 | Asked for the README write up                                          | Draft of README.md and this updated log                                   |

## Tutorials followed

- [Tutorial: Configuring a static website on Amazon S3 (Amazon S3 User Guide)](https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html)
- [Installing or updating to the latest version of the AWS CLI (AWS CLI User Guide)](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [Restrict access to an Amazon S3 origin (CloudFront Developer Guide)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)
- [Update CloudFormation stacks using change sets (CloudFormation User Guide)](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-changesets.html)
- [Using Lambda with infrastructure as code (AWS Lambda Developer Guide)](https://docs.aws.amazon.com/lambda/latest/dg/foundation-iac.html)
- [Create custom provisioning logic with custom resources (CloudFormation User Guide)](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-custom-resources.html)
- [cfn-response module (CloudFormation User Guide)](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-lambda-function-code-cfnresponsemodule.html)
- [What is Amazon VPC? (Amazon VPC User Guide)](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [VPCs and subnets (Amazon VPC User Guide)](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
- [Use ELB to distribute incoming application traffic in your Auto Scaling group (Amazon EC2 Auto Scaling User Guide)](https://docs.aws.amazon.com/autoscaling/ec2/userguide/autoscaling-load-balancer.html)
- [cfn-signal (CloudFormation Template Reference)](https://docs.aws.amazon.com/AWSCloudFormation/latest/TemplateReference/cfn-signal.html)
- [Using AWS CloudFormation with AWS CodePipeline (CloudFormation User Guide)](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/continuous-delivery-codepipeline-cfn.html)
- [MySQL on Amazon RDS versions (Amazon RDS User Guide)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MySQL.Concepts.VersionMgmt.html)
- [MySQL 8.0 End-of-Life and RDS Extended Support](https://ecorpit.com/mysql-8-0-eol-rds-extended-support-cost-migration-2026/)
- [How to install Python 3 and boto3 on Amazon EC2 (AWS re:Post)](https://repost.aws/knowledge-center/ec2-linux-python3-boto3)
- [Password management with Amazon RDS and AWS Secrets Manager (Amazon RDS User Guide)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-secrets-manager.html)

Further sources used in the write up are listed in the References section of the README.