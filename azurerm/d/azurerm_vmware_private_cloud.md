# azurerm_vmware_private_cloud

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azurerm/d/azurerm_vmware_private_cloud"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_vmware_private_cloud" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "circuit" {
  description = "returns a list of object"
  value       = data.azurerm_vmware_private_cloud.this.circuit
}

output "hcx_cloud_manager_endpoint" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.hcx_cloud_manager_endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.id
}

output "internet_connection_enabled" {
  description = "returns a bool"
  value       = data.azurerm_vmware_private_cloud.this.internet_connection_enabled
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.location
}

output "management_cluster" {
  description = "returns a list of object"
  value       = data.azurerm_vmware_private_cloud.this.management_cluster
}

output "management_subnet_cidr" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.management_subnet_cidr
}

output "network_subnet_cidr" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.network_subnet_cidr
}

output "nsxt_certificate_thumbprint" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.nsxt_certificate_thumbprint
}

output "nsxt_manager_endpoint" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.nsxt_manager_endpoint
}

output "provisioning_subnet_cidr" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.provisioning_subnet_cidr
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_vmware_private_cloud.this.tags
}

output "vcenter_certificate_thumbprint" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.vcenter_certificate_thumbprint
}

output "vcsa_endpoint" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.vcsa_endpoint
}

output "vmotion_subnet_cidr" {
  description = "returns a string"
  value       = data.azurerm_vmware_private_cloud.this.vmotion_subnet_cidr
}

output "this" {
  value = azurerm_vmware_private_cloud.this
}
```

[top](#index)