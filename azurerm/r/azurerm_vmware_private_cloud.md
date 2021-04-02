# azurerm_vmware_private_cloud

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_vmware_private_cloud" {
  source = "./modules/azurerm/r/azurerm_vmware_private_cloud"

  # internet_connection_enabled - (optional) is a type of bool
  internet_connection_enabled = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_subnet_cidr - (required) is a type of string
  network_subnet_cidr = null
  # nsxt_password - (optional) is a type of string
  nsxt_password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vcenter_password - (optional) is a type of string
  vcenter_password = null

  management_cluster = [{
    hosts = []
    id    = null
    size  = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "internet_connection_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_subnet_cidr" {
  description = "(required)"
  type        = string
}

variable "nsxt_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vcenter_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "management_cluster" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      hosts = list(string)
      id    = number
      size  = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_vmware_private_cloud" "this" {
  internet_connection_enabled = var.internet_connection_enabled
  location                    = var.location
  name                        = var.name
  network_subnet_cidr         = var.network_subnet_cidr
  nsxt_password               = var.nsxt_password
  resource_group_name         = var.resource_group_name
  sku_name                    = var.sku_name
  tags                        = var.tags
  vcenter_password            = var.vcenter_password

  dynamic "management_cluster" {
    for_each = var.management_cluster
    content {
      size = management_cluster.value["size"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "circuit" {
  description = "returns a list of object"
  value       = azurerm_vmware_private_cloud.this.circuit
}

output "hcx_cloud_manager_endpoint" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.hcx_cloud_manager_endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.id
}

output "management_subnet_cidr" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.management_subnet_cidr
}

output "nsxt_certificate_thumbprint" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.nsxt_certificate_thumbprint
}

output "nsxt_manager_endpoint" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.nsxt_manager_endpoint
}

output "provisioning_subnet_cidr" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.provisioning_subnet_cidr
}

output "vcenter_certificate_thumbprint" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.vcenter_certificate_thumbprint
}

output "vcsa_endpoint" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.vcsa_endpoint
}

output "vmotion_subnet_cidr" {
  description = "returns a string"
  value       = azurerm_vmware_private_cloud.this.vmotion_subnet_cidr
}

output "this" {
  value = azurerm_vmware_private_cloud.this
}
```

[top](#index)