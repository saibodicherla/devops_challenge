# :building_construction: Grid Singularity Devops Challenge

##  Project Description 📝

- Create an automation using Cloudformation to provision one Linux VM in AWS capable to run docker containers and with the port 80 exposed to the internet.
- Create a Dockerfile of a nginx container.
- Create a CI/CD pipeline using Jenkins to build  and deploy the container in the Linux VM
- Every code change pushed into this repository is validated by a Jenkins.


### Prerequisites ⚙️


In order to run this project, you need to have AWS Account, AWS CLI, Docker, Jenkins.

* If you don't have a AWS Account.[Create using this link](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start)
* use the [AWS CLI version 2] (https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) to install

After setting up the enviroment, you need to run
   
```bash
> aws --version
```

* Install AWS [eksctl] (https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html)

Test your environment using Kubectl and eksctl
   
```bash
> kubectl version --short --client
```

```bash
> eksctl version
```

* Finally, You need to also install [Docker] (https://docs.docker.com/engine/install/ubuntu/)

```bash
> docker -v
```


### Setup the Environment ⚙️


1. Clone the repository in your local machine

2. Add your AWS credentials in AWSCLI.

```bash
> AWS Access Key ID [****************]: 
> AWS Secret Access Key [****************]: 
> Default region name: [****] 
> Default output format: json 
```

3. Setup Jenkins Infra, To open the infra folder in your project folder and Run 'create.sh' as following command below:

```bash
> ./create.sh stackname Jenkins_infra.yml Jenkins_parameters.json
```

4. Start the Git webhook, AWS ECR credentials into Jenkins peiple and Run the build.

5. Eventually, The nginx conainter should be access through: ```bash > http://publicDNS:80 ```