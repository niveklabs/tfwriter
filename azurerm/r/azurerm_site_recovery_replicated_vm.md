# azurerm_site_recovery_replicated_vm

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
module "azurerm_site_recovery_replicated_vm" {
  source = "./modules/azurerm/r/azurerm_site_recovery_replicated_vm"

  # managed_disk - (optional) is a type of set of object
  managed_disk = [{
    disk_id                    = null
    staging_storage_account_id = null
    target_disk_type           = null
    target_replica_disk_type   = null
    target_resource_group_id   = null
  }]
  # name - (required) is a type of string
  name = null
  # network_interface - (optional) is a type of set of object
  network_interface = [{
    recovery_public_ip_address_id = null
    source_network_interface_id   = null
    target_static_ip              = null
    target_subnet_name            = null
  }]
  # recovery_replication_policy_id - (required) is a type of string
  recovery_replication_policy_id = null
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_recovery_fabric_name - (required) is a type of string
  source_recovery_fabric_name = null
  # source_recovery_protection_container_name - (required) is a type of string
  source_recovery_protection_container_name = null
  # source_vm_id - (required) is a type of string
  source_vm_id = null
  # target_availability_set_id - (optional) is a type of string
  target_availability_set_id = null
  # target_network_id - (optional) is a type of string
  target_network_id = null
  # target_recovery_fabric_id - (required) is a type of string
  target_recovery_fabric_id = null
  # target_recovery_protection_container_id - (required) is a type of string
  target_recovery_protection_container_id = null
  # target_resource_group_id - (required) is a type of string
  target_resource_group_id = null

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
variable "managed_disk" {
  description = "(optional)"
  type = set(object(
    {
      disk_id                    = string
      staging_storage_account_id = string
      target_disk_type           = string
      target_replica_disk_type   = string
      target_resource_group_id   = string
    }
  ))
  default = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_interface" {
  description = "(optional)"
  type = set(object(
    {
      recovery_public_ip_address_id = string
      source_network_interface_id   = string
      target_static_ip              = string
      target_subnet_name            = string
    }
  ))
  default = null
}

variable "recovery_replication_policy_id" {
  description = "(required)"
  type        = string
}

variable "recovery_vault_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_recovery_fabric_name" {
  description = "(required)"
  type        = string
}

variable "source_recovery_protection_container_name" {
  description = "(required)"
  type        = string
}

variable "source_vm_id" {
  description = "(required)"
  type        = string
}

variable "target_availability_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_recovery_fabric_id" {
  description = "(required)"
  type        = string
}

variable "target_recovery_protection_container_id" {
  description = "(required)"
  type        = string
}

variable "target_resource_group_id" {
  description = "(required)"
  type        = string
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
resource "azurerm_site_recovery_replicated_vm" "this" {
  # managed_disk - (optional) is a type of set of object
  managed_disk = var.managed_disk
  # name - (required) is a type of string
  name = var.name
  # network_interface - (optional) is a type of set of object
  network_interface = var.network_interface
  # recovery_replication_policy_id - (required) is a type of string
  recovery_replication_policy_id = var.recovery_replication_policy_id
  # recovery_vault_name - (required) is a type of string
  recovery_vault_name = var.recovery_vault_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # source_recovery_fabric_name - (required) is a type of string
  source_recovery_fabric_name = var.source_recovery_fabric_name
  # source_recovery_protection_container_name - (required) is a type of string
  source_recovery_protection_container_name = var.source_recovery_protection_container_name
  # source_vm_id - (required) is a type of string
  source_vm_id = var.source_vm_id
  # target_availability_set_id - (optional) is a type of string
  target_availability_set_id = var.target_availability_set_id
  # target_network_id - (optional) is a type of string
  target_network_id = var.target_network_id
  # target_recovery_fabric_id - (required) is a type of string
  target_recovery_fabric_id = var.target_recovery_fabric_id
  # target_recovery_protection_container_id - (required) is a type of string
  target_recovery_protection_container_id = var.target_recovery_protection_container_id
  # target_resource_group_id - (required) is a type of string
  target_resource_group_id = var.target_resource_group_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_site_recovery_replicated_vm.this.id
}

output "network_interface" {
  description = "returns a set of object"
  value       = azurerm_site_recovery_replicated_vm.this.network_interface
}

output "target_network_id" {
  description = "returns a string"
  value       = azurerm_site_recovery_replicated_vm.this.target_network_id
}

output "this" {
  value = azurerm_site_recovery_replicated_vm.this
}
```

[top](#index)