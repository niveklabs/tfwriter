# azurerm_virtual_machine

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
module "azurerm_virtual_machine" {
  source = "./modules/azurerm/r/azurerm_virtual_machine"

  # availability_set_id - (optional) is a type of string
  availability_set_id = null
  # delete_data_disks_on_termination - (optional) is a type of bool
  delete_data_disks_on_termination = null
  # delete_os_disk_on_termination - (optional) is a type of bool
  delete_os_disk_on_termination = null
  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_interface_ids - (required) is a type of list of string
  network_interface_ids = []
  # primary_network_interface_id - (optional) is a type of string
  primary_network_interface_id = null
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vm_size - (required) is a type of string
  vm_size = null
  # zones - (optional) is a type of list of string
  zones = []

  additional_capabilities = [{
    ultra_ssd_enabled = null
  }]

  boot_diagnostics = [{
    enabled     = null
    storage_uri = null
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    type         = null
  }]

  os_profile = [{
    admin_password = null
    admin_username = null
    computer_name  = null
    custom_data    = null
  }]

  os_profile_linux_config = [{
    disable_password_authentication = null
    ssh_keys = [{
      key_data = null
      path     = null
    }]
  }]

  os_profile_secrets = [{
    source_vault_id = null
    vault_certificates = [{
      certificate_store = null
      certificate_url   = null
    }]
  }]

  os_profile_windows_config = [{
    additional_unattend_config = [{
      component    = null
      content      = null
      pass         = null
      setting_name = null
    }]
    enable_automatic_upgrades = null
    provision_vm_agent        = null
    timezone                  = null
    winrm = [{
      certificate_url = null
      protocol        = null
    }]
  }]

  plan = [{
    name      = null
    product   = null
    publisher = null
  }]

  storage_data_disk = [{
    caching                   = null
    create_option             = null
    disk_size_gb              = null
    lun                       = null
    managed_disk_id           = null
    managed_disk_type         = null
    name                      = null
    vhd_uri                   = null
    write_accelerator_enabled = null
  }]

  storage_image_reference = [{
    id        = null
    offer     = null
    publisher = null
    sku       = null
    version   = null
  }]

  storage_os_disk = [{
    caching                   = null
    create_option             = null
    disk_size_gb              = null
    image_uri                 = null
    managed_disk_id           = null
    managed_disk_type         = null
    name                      = null
    os_type                   = null
    vhd_uri                   = null
    write_accelerator_enabled = null
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
variable "availability_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_data_disks_on_termination" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "delete_os_disk_on_termination" {
  description = "(optional)"
  type        = bool
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_interface_ids" {
  description = "(required)"
  type        = list(string)
}

variable "primary_network_interface_id" {
  description = "(optional)"
  type        = string
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vm_size" {
  description = "(required)"
  type        = string
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
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

variable "boot_diagnostics" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled     = bool
      storage_uri = string
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = list(string)
      principal_id = string
      type         = string
    }
  ))
  default = []
}

variable "os_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      admin_password = string
      admin_username = string
      computer_name  = string
      custom_data    = string
    }
  ))
  default = []
}

variable "os_profile_linux_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      disable_password_authentication = bool
      ssh_keys = list(object(
        {
          key_data = string
          path     = string
        }
      ))
    }
  ))
  default = []
}

variable "os_profile_secrets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      source_vault_id = string
      vault_certificates = list(object(
        {
          certificate_store = string
          certificate_url   = string
        }
      ))
    }
  ))
  default = []
}

variable "os_profile_windows_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      additional_unattend_config = list(object(
        {
          component    = string
          content      = string
          pass         = string
          setting_name = string
        }
      ))
      enable_automatic_upgrades = bool
      provision_vm_agent        = bool
      timezone                  = string
      winrm = list(object(
        {
          certificate_url = string
          protocol        = string
        }
      ))
    }
  ))
  default = []
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

variable "storage_data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      caching                   = string
      create_option             = string
      disk_size_gb              = number
      lun                       = number
      managed_disk_id           = string
      managed_disk_type         = string
      name                      = string
      vhd_uri                   = string
      write_accelerator_enabled = bool
    }
  ))
  default = []
}

variable "storage_image_reference" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      id        = string
      offer     = string
      publisher = string
      sku       = string
      version   = string
    }
  ))
  default = []
}

variable "storage_os_disk" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      caching                   = string
      create_option             = string
      disk_size_gb              = number
      image_uri                 = string
      managed_disk_id           = string
      managed_disk_type         = string
      name                      = string
      os_type                   = string
      vhd_uri                   = string
      write_accelerator_enabled = bool
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
resource "azurerm_virtual_machine" "this" {
  # availability_set_id - (optional) is a type of string
  availability_set_id = var.availability_set_id
  # delete_data_disks_on_termination - (optional) is a type of bool
  delete_data_disks_on_termination = var.delete_data_disks_on_termination
  # delete_os_disk_on_termination - (optional) is a type of bool
  delete_os_disk_on_termination = var.delete_os_disk_on_termination
  # license_type - (optional) is a type of string
  license_type = var.license_type
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # network_interface_ids - (required) is a type of list of string
  network_interface_ids = var.network_interface_ids
  # primary_network_interface_id - (optional) is a type of string
  primary_network_interface_id = var.primary_network_interface_id
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = var.proximity_placement_group_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vm_size - (required) is a type of string
  vm_size = var.vm_size
  # zones - (optional) is a type of list of string
  zones = var.zones

  dynamic "additional_capabilities" {
    for_each = var.additional_capabilities
    content {
      # ultra_ssd_enabled - (required) is a type of bool
      ultra_ssd_enabled = additional_capabilities.value["ultra_ssd_enabled"]
    }
  }

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      # enabled - (required) is a type of bool
      enabled = boot_diagnostics.value["enabled"]
      # storage_uri - (required) is a type of string
      storage_uri = boot_diagnostics.value["storage_uri"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      # identity_ids - (optional) is a type of list of string
      identity_ids = identity.value["identity_ids"]
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "os_profile" {
    for_each = var.os_profile
    content {
      # admin_password - (optional) is a type of string
      admin_password = os_profile.value["admin_password"]
      # admin_username - (required) is a type of string
      admin_username = os_profile.value["admin_username"]
      # computer_name - (required) is a type of string
      computer_name = os_profile.value["computer_name"]
      # custom_data - (optional) is a type of string
      custom_data = os_profile.value["custom_data"]
    }
  }

  dynamic "os_profile_linux_config" {
    for_each = var.os_profile_linux_config
    content {
      # disable_password_authentication - (required) is a type of bool
      disable_password_authentication = os_profile_linux_config.value["disable_password_authentication"]

      dynamic "ssh_keys" {
        for_each = os_profile_linux_config.value.ssh_keys
        content {
          # key_data - (required) is a type of string
          key_data = ssh_keys.value["key_data"]
          # path - (required) is a type of string
          path = ssh_keys.value["path"]
        }
      }

    }
  }

  dynamic "os_profile_secrets" {
    for_each = var.os_profile_secrets
    content {
      # source_vault_id - (required) is a type of string
      source_vault_id = os_profile_secrets.value["source_vault_id"]

      dynamic "vault_certificates" {
        for_each = os_profile_secrets.value.vault_certificates
        content {
          # certificate_store - (optional) is a type of string
          certificate_store = vault_certificates.value["certificate_store"]
          # certificate_url - (required) is a type of string
          certificate_url = vault_certificates.value["certificate_url"]
        }
      }

    }
  }

  dynamic "os_profile_windows_config" {
    for_each = var.os_profile_windows_config
    content {
      # enable_automatic_upgrades - (optional) is a type of bool
      enable_automatic_upgrades = os_profile_windows_config.value["enable_automatic_upgrades"]
      # provision_vm_agent - (optional) is a type of bool
      provision_vm_agent = os_profile_windows_config.value["provision_vm_agent"]
      # timezone - (optional) is a type of string
      timezone = os_profile_windows_config.value["timezone"]

      dynamic "additional_unattend_config" {
        for_each = os_profile_windows_config.value.additional_unattend_config
        content {
          # component - (required) is a type of string
          component = additional_unattend_config.value["component"]
          # content - (required) is a type of string
          content = additional_unattend_config.value["content"]
          # pass - (required) is a type of string
          pass = additional_unattend_config.value["pass"]
          # setting_name - (required) is a type of string
          setting_name = additional_unattend_config.value["setting_name"]
        }
      }

      dynamic "winrm" {
        for_each = os_profile_windows_config.value.winrm
        content {
          # certificate_url - (optional) is a type of string
          certificate_url = winrm.value["certificate_url"]
          # protocol - (required) is a type of string
          protocol = winrm.value["protocol"]
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

  dynamic "storage_data_disk" {
    for_each = var.storage_data_disk
    content {
      # caching - (optional) is a type of string
      caching = storage_data_disk.value["caching"]
      # create_option - (required) is a type of string
      create_option = storage_data_disk.value["create_option"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = storage_data_disk.value["disk_size_gb"]
      # lun - (required) is a type of number
      lun = storage_data_disk.value["lun"]
      # managed_disk_id - (optional) is a type of string
      managed_disk_id = storage_data_disk.value["managed_disk_id"]
      # managed_disk_type - (optional) is a type of string
      managed_disk_type = storage_data_disk.value["managed_disk_type"]
      # name - (required) is a type of string
      name = storage_data_disk.value["name"]
      # vhd_uri - (optional) is a type of string
      vhd_uri = storage_data_disk.value["vhd_uri"]
      # write_accelerator_enabled - (optional) is a type of bool
      write_accelerator_enabled = storage_data_disk.value["write_accelerator_enabled"]
    }
  }

  dynamic "storage_image_reference" {
    for_each = var.storage_image_reference
    content {
      # id - (optional) is a type of string
      id = storage_image_reference.value["id"]
      # offer - (optional) is a type of string
      offer = storage_image_reference.value["offer"]
      # publisher - (optional) is a type of string
      publisher = storage_image_reference.value["publisher"]
      # sku - (optional) is a type of string
      sku = storage_image_reference.value["sku"]
      # version - (optional) is a type of string
      version = storage_image_reference.value["version"]
    }
  }

  dynamic "storage_os_disk" {
    for_each = var.storage_os_disk
    content {
      # caching - (optional) is a type of string
      caching = storage_os_disk.value["caching"]
      # create_option - (required) is a type of string
      create_option = storage_os_disk.value["create_option"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = storage_os_disk.value["disk_size_gb"]
      # image_uri - (optional) is a type of string
      image_uri = storage_os_disk.value["image_uri"]
      # managed_disk_id - (optional) is a type of string
      managed_disk_id = storage_os_disk.value["managed_disk_id"]
      # managed_disk_type - (optional) is a type of string
      managed_disk_type = storage_os_disk.value["managed_disk_type"]
      # name - (required) is a type of string
      name = storage_os_disk.value["name"]
      # os_type - (optional) is a type of string
      os_type = storage_os_disk.value["os_type"]
      # vhd_uri - (optional) is a type of string
      vhd_uri = storage_os_disk.value["vhd_uri"]
      # write_accelerator_enabled - (optional) is a type of bool
      write_accelerator_enabled = storage_os_disk.value["write_accelerator_enabled"]
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

}
```

[top](#index)

### Outputs

```terraform
output "availability_set_id" {
  description = "returns a string"
  value       = azurerm_virtual_machine.this.availability_set_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_virtual_machine.this.id
}

output "license_type" {
  description = "returns a string"
  value       = azurerm_virtual_machine.this.license_type
}

output "this" {
  value = azurerm_virtual_machine.this
}
```

[top](#index)