# Azure DevOps Release Pipeline - CentOS Agent Deployment

This Ansible playbook is intended to be utilized within an Azure DevOps Release Pipeline, deploying a CentOS-based Azure VM. The release pipeline leverages a CentOS VM as an agent and automates the provisioning of various Azure resources, including a virtual network, subnet, public IP, security group, network interface, and the VM itself.

## Prerequisites

Before configuring the Azure DevOps release pipeline, ensure you have the following:

1. An Azure DevOps account and a project set up.

2. A CentOS VM provisioned and configured as an agent in your Azure DevOps organization.

3. Azure credentials configured in Azure DevOps with the necessary permissions to create Azure resources.

4. SSH public and private key pair for authentication. Update the `authorized_keys.pub` file path in the playbook.

## Notes

- Customize the release pipeline and playbook according to your specific Azure configurations and requirements.

- Ensure that Azure DevOps secret variables are used for sensitive information such as SSH private keys.

- Regularly review and update pipeline configurations based on changes to your infrastructure or security requirements.

- Refer to [Azure DevOps documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/) for additional information on pipeline configuration and best practices.
