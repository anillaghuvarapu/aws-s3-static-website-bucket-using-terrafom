# aws-s3-static-website-bucket-using-terrafom
This module provisions AWS S3 buckets configured for static website hosting.
Pre-requisites:
> aws cli installation
> create a IAM user and update security credentials using aws configure
> git installation
Steps to be followed:
Step1: Clone the repo using git URL 
Step2: change the S3 bucket name in main.tf , bucket name should be unique
Step3: terraform init
Step4: terraform plan --out "<filename>:
Step5: terraform apply "<filename>"
Step6: check the AWS console and access the website URL from the output
Step7: upload sample code to S3 using below command and check if website is working or not
  aws s3 cp modules/aws-s3-static-website-bucket/www/ s3://$(terraform output website_bucket_name)/ --recursive
Step8: cleanup of the environment
  aws s3 rm s3://$(terraform output website_bucket_name)/ --recursive
  terraform destroy

