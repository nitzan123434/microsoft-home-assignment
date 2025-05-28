
Before getting started, make sure to log into Azure using the az login command. Then, navigate to the terraform folder and update the terraform.tfvars file with your Subscription ID, Tenant ID, Client ID, and Client Secret. Once that's set, run terraform init, followed by terraform plan, and then terraform apply -var-file="variables.tfvars" to start building the cluster. If any issues arise regarding the deployment of the kubectl manifests, check if the new cluster is the current context with kubectl get all. If the deployment doesn't fully complete or the manifests aren't applied properly, it's often due to the Kubernetes context not being set correctly. In that case, make sure the new AKS cluster is the current context by checking with kubectl get all

Although most of the deployment was handled using Terraform, I did make use of Azure CLI for supporting actions. These CLI commands were not used as an alternative to Terraform, but rather as complementary tools that helped me better observe the system’s behavior and ensure that everything was running as expected during development.
In this application I didn’t need to utilize remote backend for the tfstate file, but I believe that it could be beneficial to some degree to create an Azure Storage account and utilize it for a remote backend for the terraform build.



