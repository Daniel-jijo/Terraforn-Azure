# Azure Linux Virtual Machine with Terraform

This repository contains Terraform code to deploy a Linux Virtual Machine (VM) in Azure, along with its associated networking and storage resources.

## Overview

This Terraform configuration creates the following Azure resources:

* **Resource Group:** A resource group to organize all resources.
* **Virtual Network (VNet):** A virtual network with a specified address space.
* **Subnet:** A subnet within the VNet.
* **Public IP Address:** A public IP address for the VM.
* **Network Security Group (NSG):** A network security group with rules to allow SSH (port 22) and HTTP (port 80) traffic.
* **Network Interface (NIC):** A network interface for the VM, associated with the subnet, public IP, and NSG.
* **Storage Account:** A storage account for boot diagnostics.
* **Linux Virtual Machine:** A Linux VM running Ubuntu 22.04 LTS.

## Prerequisites

* An Azure subscription.
* Terraform installed.
* Azure CLI or Azure PowerShell configured with your credentials.

## Usage

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

    Replace `<repository_url>` and `<repository_directory>` with your repository's URL and local directory name.

2.  **Initialize Terraform:**

    ```bash
    terraform init
    ```

3.  **Apply the Terraform configuration:**

    ```bash
    terraform apply
    ```

4.  **Confirm the changes:** Terraform will display a plan of the resources it will create. Type `yes` to confirm.

5.  **View the outputs:** After the VM is created, Terraform will display the resource group name, public IP address, and admin password.

## Variables

The following variables are used in this configuration:

* `resource_group_location`: The Azure region to deploy the resources (default: `eastus`).
* `prefix`: The prefix of the resource name (default: `win-vm-iis`).

You can customize these variables by creating a `terraform.tfvars` file or by setting environment variables.

Example `terraform.tfvars` file:

```terraform
resource_group_location = "westus2"
prefix                  = "my-custom-vm"



Outputs
The following outputs are generated:

resource_group_name: The name of the created resource group.
public_ip_address: The public IP address of the Linux VM.
admin_password: The admin password for the Linux VM (sensitive).
Cleaning Up
To destroy the created resources, run:

Bash

terraform destroy
