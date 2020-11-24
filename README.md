# gcpTerraformVM

Within a new project, use the GCP Cloud GUI to create a service account (e.g. terraform-access) and specify the compute admin role. Then, download the generated JSON file and rename it credentials.json.

From the GCP Cloud Console command line...

1. Upload the JSON file.
2. git clone https://github.com/sunsetmountain/gcpTerraformVM
3. mv credentials.json gcpTerraformVM/
4. cd gcpTerraformVM

Use the Editor to change...

1. In provider.tf, update the project name to match your existing project
2. In createVM.tf, change the machine name and type if desired

Return to the command line mode...

export GOOGLE_APPLICATION_CREDENTIALS="credentials.json"
terraform init
terraform plan

-- check to make sure things look right --

terraform build

-- see that your VM was properly created --

terraform destroy

-- see that things were cleaned up --

Note: for terraform build or terraform destroy, the option -auto-approve can be helpful to streamline things (but also dangerous -- use with caution)
