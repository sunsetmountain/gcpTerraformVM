# gcpTerraformVM

Within a new project, from the GCP Cloud Console command line...

1. git clone https://github.com/sunsetmountain/gcpTerraformVM
2. cd gcpTerraformVM

From the GCP Cloud GUI, create a service account (e.g. terraform-access) and specify the compute admin role. Then, download the generated JSON file, rename it credentials.json, and save it to your project’s directory (cloned above).

Back in the GCP Cloud Console, use the Editor to change...

1. In provider.tf, update the project name to match your existing project
2. In createVM.tf, change the machine name and type if desired

From the GCP Cloud Console command line...

terraform init
terraform plan

-- check to make sure things look right --

terraform build

-- see that your VM was properly created --

terraform destroy

-- see that things were cleaned up --

Note: for terraform build or terraform destroy, the option -auto-approve can be helpful to streamline things (but also dangerous -- use with caution)
