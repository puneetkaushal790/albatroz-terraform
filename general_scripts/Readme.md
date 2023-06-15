Clone this repo / Copy the scripts to azure cli

Make sure you give execute permission to run the script.

To give permission use

chmod +x <script.sh>

to run use : ./<script.sh>

Run the `1-Install_server.sh` to create server 


# Azure VM Creation Script (1-Install_server.sh)

This script creates a virtual machine in Azure with the specified configuration.

## Configuration

- Resource Group: AlbatrozMGA
- Location: brazilsouth
- Virtual Network: albatroz-infra
  - Address Space 1: 10.1.0.0/16
  - Address Space 2: 10.180.0.0/16
- Subnet: infra-subnet
  - Subnet Prefix: 10.180.1.0/24
- VM Size: Standard_B1s
- Image: Ubuntu2204
- Username: azureuser
- Subscription ID: f08d58c6-4005-4b43-a95c-67ec23281878
- NSG Name: my-nsg
- NSG Rule Name: allow-ssh
- NSG Rule Priority: 100

## Usage

1. Run the script in a Bash environment.
2. Follow the prompts to enter the name for the VM.
3. The script will generate an SSH key pair and check for the existence of the resource group, virtual network, and subnet.
4. If any of the resources don't exist, the script will create them.
5. A public IP address, network security group, and inbound rule for SSH will be created.
6. The script will create a network interface and a virtual machine.
7. The public IP of the VM will be retrieved, and you can SSH to the VM using the generated SSH key pair.
8. After executing the script, open the provided URL in your browser, copy the code, and paste it to login with your Azure credentials.

**Note:** Make sure to configure the variables in the script according to your requirements before running it.

# Azure CI/CD Runner Setup Script(2-install-dependency.sh)

This script sets up an Azure CI/CD runner environment by installing necessary packages and tools.

## Prerequisites

- Ubuntu or Debian-based Linux distribution

## Usage

1. Run the script in a Bash environment.
2. The script will update the repository and install the necessary packages, including curl, unzip, and jq.
3. Azure CLI will be installed by running the installation script.
4. Node.js will be installed by adding the Node.js repository and installing it using apt-get.
5. The latest version of Terraform will be fetched from the HashiCorp API.
6. Terraform will be installed by downloading the appropriate version for Linux and moving it to the /usr/local/bin directory.
7. The installations of Azure CLI, Terraform, Node.js, and npm will be verified.
8. After executing the script, you should see the versions of each installed tool displayed.

**Note:** Make sure to run the script with appropriate permissions, as some commands require sudo access. It is also recommended to review the script and customize it according to your specific requirements before running it.

# GitHub Actions Runner Setup Script(3-configure-runner.sh)

This script sets up a GitHub Actions runner by downloading the runner package, configuring it, and creating a service to keep the runner running.

## Prerequisites

- Linux environment
- GitHub repository URL
- Runner token for the repository

## Usage

1. Create a folder to host the runner by running the following command:

2. Run the script in a Bash environment.

3. The script will prompt for the GitHub repository URL. Enter the URL when prompted.

4. The script will prompt for the runner token. Provide the token when prompted. You can find the token in your GitHub repository settings under Actions > Runners > New self-hosted runner > Configure.

5. The GitHub Actions runner package will be downloaded based on the specified runner version.

6. The runner package will be extracted.

7. The runner will be configured by running the `./config.sh` script with the provided repository URL and token.

8. A service will be created to keep the runner running.

9. The service will be started.

10. The status of the service will be checked to ensure that the runner is running.

**Note:** Make sure to run the script with appropriate permissions, as some commands may require sudo access. It is also recommended to review the script and customize it according to your specific requirements before running it.

