# Terraform installation and configuration

Downloading and unpacking Terraform binary by the following manual https://www.terraform.io/intro/getting-started/install.html

```
curl -O https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip
mkdir /bin/terraform
unzip terraform_0.11.8_linux_amd64.zip -d /bin/terraform
export PATH=$PATH:/bin/terraform

terraform --version
```
