#Laucn EC2 in certain regions
## Preventive control
Use SCP from the account and OU level
https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples_general.html

Use IAM condition key for single user group or user, as below blog shows
https://aws.amazon.com/blogs/security/easier-way-to-control-access-to-aws-regions-using-iam-policies/

## Detective control
How to detect the launch of ec2 in non-approved region?
### Cloudtrail
Deploy an eventbridge rule in each non-approved region to monitor the API call ec2:runinstance, then send alert to email by using SNS
### Inspector
Deploy an eventbridge rule in each non-approved region to monitor inspector coverage alert,then send alert to email by using SNS
Deploy the [cloudformation template] (inspector2-coverage-alert.yml)to each region by either CLI or Cloudformation Stacksets for multiple accounts in an Organizations.
