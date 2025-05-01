# MIGRATION TO TERRAFORM & DRIFT DETECTION

https://youtu.be/-4IMy5ihiiU

We use terraform import command for migration

1.
example -- right a main.tf file

import{
id = "instance_id"
to = aws_instance.example
}

1. run commnads -
   i. terraform init
   ii. terraform plan -generate-config-out=<name of config file>(generatefile.tf)

2. copy the block of code from gerneratedfile.tf and paste it in main.tf
   now delete gerneratedfile.tf.

3. use commads -
     i. terraform init
     ii. terraform import aws_instance.example <instance_id>
     iii. terraform plan and terraform apply


------------------------------------------------------------------------

Drift detection -- 

1. terraform refresh (it refresh statefile) condition you need to run as cron job
2a.  Configuare strict IAM roles - even devops can not login aws - take approval for that
2b. you can performs some audit logs, perform automation, where you can identify if someone make manual changes to the resources configured by terraform, those audit logs can be used by any other monitoring tools. there I configure Iam user.
if changes is done by manually then that show the IAM user or name then you can send notification.
   
