# aviatrix_arm_peer

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_arm_peer" {
  source = "./modules/aviatrix/r/aviatrix_arm_peer"

  # account_name1 - (required) is a type of string
  account_name1 = null
  # account_name2 - (required) is a type of string
  account_name2 = null
  # vnet_name_resource_group1 - (required) is a type of string
  vnet_name_resource_group1 = null
  # vnet_name_resource_group2 - (required) is a type of string
  vnet_name_resource_group2 = null
  # vnet_reg1 - (required) is a type of string
  vnet_reg1 = null
  # vnet_reg2 - (required) is a type of string
  vnet_reg2 = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name1" {
  description = "(required) - This parameter represents the name of an Azure Cloud-Account in Aviatrix controller."
  type        = string
}

variable "account_name2" {
  description = "(required) - This parameter represents the name of an Azure Cloud-Account in Aviatrix controller."
  type        = string
}

variable "vnet_name_resource_group1" {
  description = "(required) - VNet-Name of Azure cloud."
  type        = string
}

variable "vnet_name_resource_group2" {
  description = "(required) - VNet-Name of Azure cloud."
  type        = string
}

variable "vnet_reg1" {
  description = "(required) - Region of Azure cloud."
  type        = string
}

variable "vnet_reg2" {
  description = "(required) - Region of Azure cloud."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_arm_peer" "this" {
  # account_name1 - (required) is a type of string
  account_name1 = var.account_name1
  # account_name2 - (required) is a type of string
  account_name2 = var.account_name2
  # vnet_name_resource_group1 - (required) is a type of string
  vnet_name_resource_group1 = var.vnet_name_resource_group1
  # vnet_name_resource_group2 - (required) is a type of string
  vnet_name_resource_group2 = var.vnet_name_resource_group2
  # vnet_reg1 - (required) is a type of string
  vnet_reg1 = var.vnet_reg1
  # vnet_reg2 - (required) is a type of string
  vnet_reg2 = var.vnet_reg2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_arm_peer.this.id
}

output "vnet_cidr1" {
  description = "returns a list of string"
  value       = aviatrix_arm_peer.this.vnet_cidr1
}

output "vnet_cidr2" {
  description = "returns a list of string"
  value       = aviatrix_arm_peer.this.vnet_cidr2
}

output "this" {
  value = aviatrix_arm_peer.this
}
```

[top](#index)