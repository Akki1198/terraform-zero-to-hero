Terraform workspace is used to create resources in different Environments.
we use some commands to do that -
1. terraform workspace new (name of Environment)
2. terraform workspace select  (name of Environment)  - used to switch the stage
3. terraform workspace show (show the current stage)

Two ways to create workspace -
1. create dev.tfvars, stage.tfvars and prod.tfvars
2. terraform apply -var-file=dev.tfvarss
