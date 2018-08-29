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
sudo apt-get install docker-ce

sudo docker run hello-world
```

Running Terraform

```
docker run -i -t hashicorp/terraform:light plan main.tf

docker run -i -t hashicorp/terraform:full plan main.tf
```
