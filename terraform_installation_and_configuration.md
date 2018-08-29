# Terraform installation and configuration

Downloading and unpacking Terraform binary by the following manual https://www.terraform.io/intro/getting-started/install.html

```
curl -O https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip
mkdir /bin/terraform
unzip terraform_0.11.8_linux_amd64.zip -d /bin/terraform
export PATH=$PATH:/bin/terraform

terraform --version
```

Running Terraform in Docker
https://hub.docker.com/r/hashicorp/terraform/

Installing Docker https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-repository

Setting up the Docker repo

```
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

Installing Docker CE

```
sudo apt-get update

sudo apt-get install docker-ce

sudo docker run hello-world
```

Setting variables

```
vi terraform.tfvars
```

Running Terraform https://github.com/LeapBeyond/terraform-tutorials/wiki/Hands-on-3:-Terraform-syntax

```
# Initialize terraform in the project directory
> docker run -it --rm -v $(pwd):/app/ -w /app/ hashicorp/terraform:light init
# validate your files in the app subdirectory
> docker run -it --rm -v $(pwd):/app/ -w /app/ hashicorp/terraform:light validate /app
# plan the changes needed, requiring your secret key ...
> docker run -it --rm -v $(pwd):/app/ -w /app/ -v $HOME/.aws:/app/.aws hashicorp/terraform:light plan /app
# Then apply!
> docker run -it --rm -v $(pwd):/app/ -w /app/ -v $HOME/.aws:/app/.aws hashicorp/terraform:light apply /app
```
