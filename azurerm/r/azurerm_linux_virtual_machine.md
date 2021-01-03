# azurerm_linux_virtual_machine

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_linux_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_linux_virtual_machine"

  # admin_password - (optional) is a type of string
  admin_password = null
  # admin_username - (required) is a type of string
  admin_username = null
  # allow_extension_operations - (optional) is a type of bool
  allow_extension_operations = null
  # availability_set_id - (optional) is a type of string
  availability_set_id = null
  # computer_name - (optional) is a type of string
  computer_name = null
  # custom_data - (optional) is a type of string
  custom_data = null
  # dedicated_host_id - (optional) is a type of string
  dedicated_host_id = null
  # disable_password_authentication - (optional) is a type of bool
  disable_password_authentication = null
  # encryption_at_host_enabled - (optional) is a type of bool
  encryption_at_host_enabled = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # extensions_time_budget - (optional) is a type of string
  extensions_time_budget = null
  # location - (required) is a type of string
  location = null
  # max_bid_price - (optional) is a type of number
  max_bid_price = null
  # name - (required) is a type of string
  name = null
  # network_interface_ids - (required) is a type of list of string
  network_interface_ids = []
  # priority - (optional) is a type of string
  priority = null
  # provision_vm_agent - (optional) is a type of bool
  provision_vm_agent = null
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # size - (required) is a type of string
  size = null
  # source_image_id - (optional) is a type of string
  source_image_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_machine_scale_set_id - (optional) is a type of string
  virtual_machine_scale_set_id = null
  # zone - (optional) is a type of string
  zone = null

  additional_capabilities = [{
    ultra_ssd_enabled = null
  }]

  admin_ssh_key = [{
    public_key = null
    username   = null
  }]

  boot_diagnostics = [{
    storage_account_uri = null
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  os_disk = [{
    caching = null
    diff_disk_settings = [{
      option = null
    }]
    disk_encryption_set_id    = null
    disk_size_gb              = null
    name                      = null
    storage_account_type      = null
    write_accelerator_enabled = null
  }]

  plan = [{
    name      = null
    product   = null
    publisher = null
  }]

  secret = [{
    certificate = [{
      url = null
    }]
    key_vault_id = null
  }]

  source_image_reference = [{
    offer     = null
    publisher = null
    sku       = null
    version   = null
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
variable "admin_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_username" {
  description = "(required)"
  type        = string
}

variable "allow_extension_operations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "computer_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dedicated_host_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_password_authentication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "encryption_at_host_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "eviction_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extensions_time_budget" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_bid_price" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_interface_ids" {
  description = "(required)"
  type        = list(string)
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provision_vm_agent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "proximity_placement_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = string
}

variable "source_image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_machine_scale_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "additional_capabilities" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ultra_ssd_enabled = bool
    }
  ))
  default = []
}

variable "admin_ssh_key" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      public_key = string
      username   = string
    }
  ))
  default = []
}

variable "boot_diagnostics" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      storage_account_uri = string
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = set(string)
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "os_disk" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      caching = string
      diff_disk_settings = list(object(
        {
          option = string
        }
      ))
      disk_encryption_set_id    = string
      disk_size_gb              = number
      name                      = string
      storage_account_type      = string
      write_accelerator_enabled = bool
    }
  ))
}

variable "plan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name      = string
      product   = string
      publisher = string
    }
  ))
  default = []
}

variable "secret" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate = set(object(
        {
          url = string
        }
      ))
      key_vault_id = string
    }
  ))
  default = []
}

variable "source_image_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      offer     = string
      publisher = string
      sku       = string
      version   = string
    }
  ))
  default = []
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
resource "azurerm_linux_virtual_machine" "this" {
  admin_password                  = var.admin_password
  admin_username                  = var.admin_username
  allow_extension_operations      = var.allow_extension_operations
  availability_set_id             = var.availability_set_id
  computer_name                   = var.computer_name
  custom_data                     = var.custom_data
  dedicated_host_id               = var.dedicated_host_id
  disable_password_authentication = var.disable_password_authentication
  encryption_at_host_enabled      = var.encryption_at_host_enabled
  eviction_policy                 = var.eviction_policy
  extensions_time_budget          = var.extensions_time_budget
  location                        = var.location
  max_bid_price                   = var.max_bid_price
  name                            = var.name
  network_interface_ids           = var.network_interface_ids
  priority                        = var.priority
  provision_vm_agent              = var.provision_vm_agent
  proximity_placement_group_id    = var.proximity_placement_group_id
  resource_group_name             = var.resource_group_name
  size                            = var.size
  source_image_id                 = var.source_image_id
  tags                            = var.tags
  virtual_machine_scale_set_id    = var.virtual_machine_scale_set_id
  zone                            = var.zone

  dynamic "additional_capabilities" {
    for_each = var.additional_capabilities
    content {
      ultra_ssd_enabled = additional_capabilities.value["ultra_ssd_enabled"]
    }
  }

  dynamic "admin_ssh_key" {
    for_each = var.admin_ssh_key
    content {
      public_key = admin_ssh_key.value["public_key"]
      username   = admin_ssh_key.value["username"]
    }
  }

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      storage_account_uri = boot_diagnostics.value["storage_account_uri"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      identity_ids = identity.value["identity_ids"]
      type         = identity.value["type"]
    }
  }

  dynamic "os_disk" {
    for_each = var.os_disk
    content {
      caching                   = os_disk.value["caching"]
      disk_encryption_set_id    = os_disk.value["disk_encryption_set_id"]
      disk_size_gb              = os_disk.value["disk_size_gb"]
      name                      = os_disk.value["name"]
      storage_account_type      = os_disk.value["storage_account_type"]
      write_accelerator_enabled = os_disk.value["write_accelerator_enabled"]

      dynamic "diff_disk_settings" {
        for_each = os_disk.value.diff_disk_settings
        content {
          option = diff_disk_settings.value["option"]
        }
      }

    }
  }

  dynamic "plan" {
    for_each = var.plan
    content {
      name      = plan.value["name"]
      product   = plan.value["product"]
      publisher = plan.value["publisher"]
    }
  }

  dynamic "secret" {
    for_each = var.secret
    content {
      key_vault_id = secret.value["key_vault_id"]

      dynamic "certificate" {
        for_each = secret.value.certificate
        content {
          url = certificate.value["url"]
        }
      }

    }
  }

  dynamic "source_image_reference" {
    for_each = var.source_image_reference
    content {
      offer     = source_image_reference.value["offer"]
      publisher = source_image_reference.value["publisher"]
      sku       = source_image_reference.value["sku"]
      version   = source_image_reference.value["version"]
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
output "computer_name" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.computer_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.id
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_linux_virtual_machine.this.private_ip_addresses
}

output "public_ip_address" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.public_ip_address
}

output "public_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_linux_virtual_machine.this.public_ip_addresses
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.virtual_machine_id
}

output "zone" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine.this.zone
}

output "this" {
  value = azurerm_linux_virtual_machine.this
}
```

[top](#index)