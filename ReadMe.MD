# Azure VM Deployment Playbook

This Ansible playbook automates the deployment of an Azure Virtual Machine (VM) with specific configurations, including a virtual network, subnet, public IP, security group, network interface, and the VM itself. The playbook is designed to create a CentOS-based VM.

## Prerequisites

Before running this playbook, ensure you have the following:

1. Ansible installed on your local machine.

2. Azure credentials set up, including the necessary permissions to create resources.

3. SSH public and private key pair for authentication. Update the `authorized_keys.pub` file path in the playbook.

## Playbook Overview

The playbook performs the following tasks:

1. Creates a virtual network with the name `awesomevnet` and the address prefix `10.10.0.0/16`.

2. Adds a subnet named `awesomesubnet1` with the address prefix `10.10.0.0/24` to the virtual network.

3. Creates a static public IP address named `awesomepublicip1`.

4. Creates a security group named `awesomesecgroup1` that allows inbound SSH traffic on port 22.

5. Creates a network interface named `awesomenic1` with the specified configurations, including the associated subnet, public IP, and security group.

6. Creates an Azure VM named `awesomevm1` with CentOS 7.5 image, Standard_D2s_v3 size, and specific configurations such as the admin username, SSH public key, and network interface.

## Usage

1. Ensure you have Ansible installed. If not, you can install it using:

    ```bash
 
    sudo yum update -y

    sudo yum install -y python3-pip

    sudo pip3 install --upgrade pip

    pip3 install "ansible==2.9.17"

    pip3 install ansible[azure]
    ```

2. Update the playbook variables in the `vars` section according to your requirements, such as `resource_group_name`, `vm_name`, and others.

3. Ensure you have the SSH public and private key pair for authentication. Update the `authorized_keys.pub` file path accordingly.

4. Run the playbook using the following command:

    ```bash
    ansible-playbook your_playbook.yml
    ```

5. The playbook will create the specified Azure resources and deploy the CentOS VM.

## Notes

- Ensure that your Azure credentials are correctly configured.

- Customize the playbook further based on your specific needs, such as VM size, image version, or additional configurations.

- Monitor the playbook execution for any errors or prompts for user input.

- Adjust security group rules and configurations based on your security requirements.

- Review Azure documentation for more details on [Azure Ansible Modules](https://docs.microsoft.com/en-us/azure/developer/ansible/).
