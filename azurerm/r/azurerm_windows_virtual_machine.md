# azurerm_windows_virtual_machine

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
module "azurerm_windows_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_windows_virtual_machine"

  # admin_password - (required) is a type of string
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
  # enable_automatic_updates - (optional) is a type of bool
  enable_automatic_updates = null
  # encryption_at_host_enabled - (optional) is a type of bool
  encryption_at_host_enabled = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # extensions_time_budget - (optional) is a type of string
  extensions_time_budget = null
  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # max_bid_price - (optional) is a type of number
  max_bid_price = null
  # name - (required) is a type of string
  name = null
  # network_interface_ids - (required) is a type of list of string
  network_interface_ids = []
  # patch_mode - (optional) is a type of string
  patch_mode = null
  # platform_fault_domain - (optional) is a type of number
  platform_fault_domain = null
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
  # timezone - (optional) is a type of string
  timezone = null
  # virtual_machine_scale_set_id - (optional) is a type of string
  virtual_machine_scale_set_id = null
  # zone - (optional) is a type of string
  zone = null

  additional_capabilities = [{
    ultra_ssd_enabled = null
  }]

  additional_unattend_content = [{
    content = null
    setting = null
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
      store = null
      url   = null
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

  winrm_listener = [{
    certificate_url = null
    protocol        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admin_password" {
  description = "(required)"
  type        = string
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

variable "enable_automatic_updates" {
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

variable "license_type" {
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

variable "patch_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform_fault_domain" {
  description = "(optional)"
  type        = number
  default     = null
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

variable "timezone" {
  description = "(optional)"
  type        = string
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

variable "additional_unattend_content" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      content = string
      setting = string
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
          store = string
          url   = string
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

variable "winrm_listener" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_url = string
      protocol        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_windows_virtual_machine" "this" {
  # admin_password - (required) is a type of string
  admin_password = var.admin_password
  # admin_username - (required) is a type of string
  admin_username = var.admin_username
  # allow_extension_operations - (optional) is a type of bool
  allow_extension_operations = var.allow_extension_operations
  # availability_set_id - (optional) is a type of string
  availability_set_id = var.availability_set_id
  # computer_name - (optional) is a type of string
  computer_name = var.computer_name
  # custom_data - (optional) is a type of string
  custom_data = var.custom_data
  # dedicated_host_id - (optional) is a type of string
  dedicated_host_id = var.dedicated_host_id
  # enable_automatic_updates - (optional) is a type of bool
  enable_automatic_updates = var.enable_automatic_updates
  # encryption_at_host_enabled - (optional) is a type of bool
  encryption_at_host_enabled = var.encryption_at_host_enabled
  # eviction_policy - (optional) is a type of string
  eviction_policy = var.eviction_policy
  # extensions_time_budget - (optional) is a type of string
  extensions_time_budget = var.extensions_time_budget
  # license_type - (optional) is a type of string
  license_type = var.license_type
  # location - (required) is a type of string
  location = var.location
  # max_bid_price - (optional) is a type of number
  max_bid_price = var.max_bid_price
  # name - (required) is a type of string
  name = var.name
  # network_interface_ids - (required) is a type of list of string
  network_interface_ids = var.network_interface_ids
  # patch_mode - (optional) is a type of string
  patch_mode = var.patch_mode
  # platform_fault_domain - (optional) is a type of number
  platform_fault_domain = var.platform_fault_domain
  # priority - (optional) is a type of string
  priority = var.priority
  # provision_vm_agent - (optional) is a type of bool
  provision_vm_agent = var.provision_vm_agent
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = var.proximity_placement_group_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # size - (required) is a type of string
  size = var.size
  # source_image_id - (optional) is a type of string
  source_image_id = var.source_image_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # virtual_machine_scale_set_id - (optional) is a type of string
  virtual_machine_scale_set_id = var.virtual_machine_scale_set_id
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "additional_capabilities" {
    for_each = var.additional_capabilities
    content {
      # ultra_ssd_enabled - (optional) is a type of bool
      ultra_ssd_enabled = additional_capabilities.value["ultra_ssd_enabled"]
    }
  }

  dynamic "additional_unattend_content" {
    for_each = var.additional_unattend_content
    content {
      # content - (required) is a type of string
      content = additional_unattend_content.value["content"]
      # setting - (required) is a type of string
      setting = additional_unattend_content.value["setting"]
    }
  }

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      # storage_account_uri - (optional) is a type of string
      storage_account_uri = boot_diagnostics.value["storage_account_uri"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      # identity_ids - (optional) is a type of set of string
      identity_ids = identity.value["identity_ids"]
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "os_disk" {
    for_each = var.os_disk
    content {
      # caching - (required) is a type of string
      caching = os_disk.value["caching"]
      # disk_encryption_set_id - (optional) is a type of string
      disk_encryption_set_id = os_disk.value["disk_encryption_set_id"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = os_disk.value["disk_size_gb"]
      # name - (optional) is a type of string
      name = os_disk.value["name"]
      # storage_account_type - (required) is a type of string
      storage_account_type = os_disk.value["storage_account_type"]
      # write_accelerator_enabled - (optional) is a type of bool
      write_accelerator_enabled = os_disk.value["write_accelerator_enabled"]

      dynamic "diff_disk_settings" {
        for_each = os_disk.value.diff_disk_settings
        content {
          # option - (required) is a type of string
          option = diff_disk_settings.value["option"]
        }
      }

    }
  }

  dynamic "plan" {
    for_each = var.plan
    content {
      # name - (required) is a type of string
      name = plan.value["name"]
      # product - (required) is a type of string
      product = plan.value["product"]
      # publisher - (required) is a type of string
      publisher = plan.value["publisher"]
    }
  }

  dynamic "secret" {
    for_each = var.secret
    content {
      # key_vault_id - (required) is a type of string
      key_vault_id = secret.value["key_vault_id"]

      dynamic "certificate" {
        for_each = secret.value.certificate
        content {
          # store - (required) is a type of string
          store = certificate.value["store"]
          # url - (required) is a type of string
          url = certificate.value["url"]
        }
      }

    }
  }

  dynamic "source_image_reference" {
    for_each = var.source_image_reference
    content {
      # offer - (required) is a type of string
      offer = source_image_reference.value["offer"]
      # publisher - (required) is a type of string
      publisher = source_image_reference.value["publisher"]
      # sku - (required) is a type of string
      sku = source_image_reference.value["sku"]
      # version - (required) is a type of string
      version = source_image_reference.value["version"]
    }
  }

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

  dynamic "winrm_listener" {
    for_each = var.winrm_listener
    content {
      # certificate_url - (optional) is a type of string
      certificate_url = winrm_listener.value["certificate_url"]
      # protocol - (required) is a type of string
      protocol = winrm_listener.value["protocol"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "computer_name" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.computer_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.id
}

output "private_ip_address" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.private_ip_address
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_windows_virtual_machine.this.private_ip_addresses
}

output "public_ip_address" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.public_ip_address
}

output "public_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_windows_virtual_machine.this.public_ip_addresses
}

output "virtual_machine_id" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.virtual_machine_id
}

output "zone" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine.this.zone
}

output "this" {
  value = azurerm_windows_virtual_machine.this
}
```

[top](#index)