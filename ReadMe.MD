# Azure DevOps Release Pipeline - CentOS Agent Deployment

This Ansible playbook is intended to be utilized within an Azure DevOps Release Pipeline, deploying a CentOS-based Azure VM. The release pipeline leverages a CentOS VM as an agent and automates the provisioning of various Azure resources, including a virtual network, subnet, public IP, security group, network interface, and the VM itself.

## Prerequisites

Before configuring the Azure DevOps release pipeline, ensure you have the following:

1. An Azure DevOps account and a project set up.

2. A CentOS VM provisioned and configured as an agent in your Azure DevOps organization.

3. Azure credentials configured in Azure DevOps with the necessary permissions to create Azure resources.

4. SSH public and private key pair for authentication. Update the `authorized_keys.pub` file path in the playbook.

## Monitoring and Alerts

This project integrates Azure Monitor for monitoring CPU metrics on the deployed VM. Follow these steps to set up monitoring and alerts:

1. Ensure the Azure Monitor Ansible Collection is installed by running:
   ```bash
   ansible-galaxy collection install azure.monitor
   ```

2. Update the playbook with the CPU metrics collection tasks.

3. Configure Azure Monitor alerts based on the collected metrics:
   - Navigate to the Azure Portal and access Azure Monitor.
   - In the left-hand menu, select "Monitor" and then "Alerts."
   - Click on "+ New alert rule" to define the alert conditions.
   - Set up actions to be taken when the alert is triggered.
   - Save the alert rule.

4. View CPU metrics in Azure Monitor:
   - In the Azure Portal, navigate to "Monitor" and then "Metrics."
   - Select the resource type (e.g., "Virtual Machines") and metric (e.g., "Processor Time").
   - Adjust time ranges and filters as needed.
   - Review the metrics graph for CPU usage over time.

5. Regularly review and update alert rules based on changing infrastructure needs.


## Notes

- Customize the release pipeline and playbook according to your specific Azure configurations and requirements.

- Ensure that Azure DevOps secret variables are used for sensitive information such as SSH private keys.

- Regularly review and update pipeline configurations based on changes to your infrastructure or security requirements.

- Refer to [Azure DevOps documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/) for additional information on pipeline configuration and best practices.
