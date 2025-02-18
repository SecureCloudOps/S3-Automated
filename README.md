# Automating S3 Bucket Deployment with Terraform

**Author:** Mohamed Mohamed  
**Email:** mohamed0395@gmail.com

---
![Image](https://i.imgur.com/ZD1uxme.png)

---


### Introduction

In this project, I will show you how I created a S3 bucket using Terraform. The
goal is to cut out the manual work of creating new resources in the cloud, which reduces the chances of errors.

### What is Terraform?

Terraform is is a tool that helps me build and manage cloud infrastructure using
code. Terraform is one of the most popular tools used for infrastructure as code (IaC),
which is a way to manage setting up your resources instead creating resources
one by one in the Console.

Terraform uses configuration files to define and manage infrastructure. It
describes the desired state of the infrastructure and Terrform understands on
how to achieve it.

![Image](https://i.imgur.com/sNztD0J.png)

---

## Configuration files

The configuration is structured in blocks (Resource,Provider) with .tf files using
HashiCorp Configuration Language(HCL). 

The advantage of doing this is
blocks provide clear visual hierarchy and nesting, making complex code easy
to read and maintain

![Image](https://i.imgur.com/kzAErVe.png)


## My main.tf configuration has three blocks

The first block indicates the provider, in this case will be AWS. The second
block indicates the actual resource that needs to be created, in this case will be
a s3 bucket. The third block manages the public access policies for the s3
bucket.

![Image](https://i.imgur.com/bYCEFVT.png)

---

## Terraform commands

I ran `terraform init` to initialize my working directory, download required
provider plugins, and set up the backend for storing state files. This is always
the first command needed before any terraform operations.

![Image](https://imgur.com/zKYKRHz.png)

![Image](https://imgur.com/qk6W7yD.png) 

Next, I ran `terraform plan` to preview the changes Terraform will make to my infrastructure. It shows what resources will be added, modified, or deleted before actually applying the changes.

![Image](https://imgur.com/uYtNPtW.png)

### AWS CLI and Access Keys

When I tried to plan my Terraform configuration, I received an error message
that says 'No valid credential sources found' , because I didn't have my
computer installed with AWS CLI and also missing my credentials.

![Image](https://i.imgur.com/G1iecWt.png)

To resolve my error, first I installed AWS CLI, which is is a powerful tool that lets
me manage my AWS services from my terminal. Instead of having to use the
AWS Management Console, I can now run text commands from my local
machine.

![Image](https://imgur.com/CpZ3Ljb.png)

![Image](https://imgur.com/pG2dedb.png)

### Lanching the S3 Bucket

I ran `terraform apply` to execute the s3 bucket defined in my .tf files and create
infrastructure resources. Running `terraform apply` will affect my AWS account
by creating, the intended resources.

The sequence of running terraform init, plan, and apply is crucial because, it
initializes the back-end, generates an execution plan, and applies the desired
configuration changes in a predictable and safe order.

---


![Image](https://i.imgur.com/xot1szr.png)

---

---
