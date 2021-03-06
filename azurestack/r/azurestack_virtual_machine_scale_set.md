# azurestack_virtual_machine_scale_set

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_virtual_machine_scale_set" {
  source = "./modules/azurestack/r/azurestack_virtual_machine_scale_set"

  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # overprovision - (optional) is a type of bool
  overprovision = null
  # priority - (optional) is a type of string
  priority = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # single_placement_group - (optional) is a type of bool
  single_placement_group = null
  # tags - (optional) is a type of map of string
  tags = {}
  # upgrade_policy_mode - (required) is a type of string
  upgrade_policy_mode = null

  extension = [{
    auto_upgrade_minor_version = null
    name                       = null
    protected_settings         = null
    publisher                  = null
    settings                   = null
    type                       = null
    type_handler_version       = null
  }]

  identity = [{
    principal_id = null
    type         = null
  }]

  network_profile = [{
    ip_configuration = [{
      application_gateway_backend_address_pool_ids = []
      load_balancer_backend_address_pool_ids       = []
      load_balancer_inbound_nat_rules_ids          = []
      name                                         = null
      primary                                      = null
      public_ip_address_configuration = [{
        domain_name_label = null
        idle_timeout      = null
        name              = null
      }]
      subnet_id = null
    }]
    name                      = null
    network_security_group_id = null
    primary                   = null
  }]

  os_profile = [{
    admin_password       = null
    admin_username       = null
    computer_name_prefix = null
    custom_data          = null
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

  sku = [{
    capacity = null
    name     = null
    tier     = null
  }]

  storage_profile_data_disk = [{
    caching           = null
    create_option     = null
    disk_size_gb      = null
    lun               = null
    managed_disk_type = null
  }]

  storage_profile_image_reference = [{
    id        = null
    offer     = null
    publisher = null
    sku       = null
    version   = null
  }]

  storage_profile_os_disk = [{
    caching           = null
    create_option     = null
    image             = null
    managed_disk_type = null
    name              = null
    os_type           = null
    vhd_containers    = []
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "overprovision" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "single_placement_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "upgrade_policy_mode" {
  description = "(required)"
  type        = string
}

variable "extension" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auto_upgrade_minor_version = bool
      name                       = string
      protected_settings         = string
      publisher                  = string
      settings                   = string
      type                       = string
      type_handler_version       = string
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      type         = string
    }
  ))
  default = []
}

variable "network_profile" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      ip_configuration = list(object(
        {
          application_gateway_backend_address_pool_ids = set(string)
          load_balancer_backend_address_pool_ids       = set(string)
          load_balancer_inbound_nat_rules_ids          = set(string)
          name                                         = string
          primary                                      = bool
          public_ip_address_configuration = list(object(
            {
              domain_name_label = string
              idle_timeout      = number
              name              = string
            }
          ))
          subnet_id = string
        }
      ))
      name                      = string
      network_security_group_id = string
      primary                   = bool
    }
  ))
}

variable "os_profile" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_password       = string
      admin_username       = string
      computer_name_prefix = string
      custom_data          = string
    }
  ))
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      name      = string
      product   = string
      publisher = string
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
      tier     = string
    }
  ))
}

variable "storage_profile_data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      caching           = string
      create_option     = string
      disk_size_gb      = number
      lun               = number
      managed_disk_type = string
    }
  ))
  default = []
}

variable "storage_profile_image_reference" {
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

variable "storage_profile_os_disk" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      caching           = string
      create_option     = string
      image             = string
      managed_disk_type = string
      name              = string
      os_type           = string
      vhd_containers    = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_virtual_machine_scale_set" "this" {
  # license_type - (optional) is a type of string
  license_type = var.license_type
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # overprovision - (optional) is a type of bool
  overprovision = var.overprovision
  # priority - (optional) is a type of string
  priority = var.priority
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # single_placement_group - (optional) is a type of bool
  single_placement_group = var.single_placement_group
  # tags - (optional) is a type of map of string
  tags = var.tags
  # upgrade_policy_mode - (required) is a type of string
  upgrade_policy_mode = var.upgrade_policy_mode

  dynamic "extension" {
    for_each = var.extension
    content {
      # auto_upgrade_minor_version - (optional) is a type of bool
      auto_upgrade_minor_version = extension.value["auto_upgrade_minor_version"]
      # name - (required) is a type of string
      name = extension.value["name"]
      # protected_settings - (optional) is a type of string
      protected_settings = extension.value["protected_settings"]
      # publisher - (required) is a type of string
      publisher = extension.value["publisher"]
      # settings - (optional) is a type of string
      settings = extension.value["settings"]
      # type - (required) is a type of string
      type = extension.value["type"]
      # type_handler_version - (required) is a type of string
      type_handler_version = extension.value["type_handler_version"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "network_profile" {
    for_each = var.network_profile
    content {
      # name - (required) is a type of string
      name = network_profile.value["name"]
      # network_security_group_id - (optional) is a type of string
      network_security_group_id = network_profile.value["network_security_group_id"]
      # primary - (required) is a type of bool
      primary = network_profile.value["primary"]

      dynamic "ip_configuration" {
        for_each = network_profile.value.ip_configuration
        content {
          # application_gateway_backend_address_pool_ids - (optional) is a type of set of string
          application_gateway_backend_address_pool_ids = ip_configuration.value["application_gateway_backend_address_pool_ids"]
          # load_balancer_backend_address_pool_ids - (optional) is a type of set of string
          load_balancer_backend_address_pool_ids = ip_configuration.value["load_balancer_backend_address_pool_ids"]
          # load_balancer_inbound_nat_rules_ids - (optional) is a type of set of string
          load_balancer_inbound_nat_rules_ids = ip_configuration.value["load_balancer_inbound_nat_rules_ids"]
          # name - (required) is a type of string
          name = ip_configuration.value["name"]
          # primary - (optional) is a type of bool
          primary = ip_configuration.value["primary"]
          # subnet_id - (required) is a type of string
          subnet_id = ip_configuration.value["subnet_id"]

          dynamic "public_ip_address_configuration" {
            for_each = ip_configuration.value.public_ip_address_configuration
            content {
              # domain_name_label - (required) is a type of string
              domain_name_label = public_ip_address_configuration.value["domain_name_label"]
              # idle_timeout - (required) is a type of number
              idle_timeout = public_ip_address_configuration.value["idle_timeout"]
              # name - (required) is a type of string
              name = public_ip_address_configuration.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "os_profile" {
    for_each = var.os_profile
    content {
      # admin_password - (optional) is a type of string
      admin_password = os_profile.value["admin_password"]
      # admin_username - (required) is a type of string
      admin_username = os_profile.value["admin_username"]
      # computer_name_prefix - (required) is a type of string
      computer_name_prefix = os_profile.value["computer_name_prefix"]
      # custom_data - (optional) is a type of string
      custom_data = os_profile.value["custom_data"]
    }
  }

  dynamic "os_profile_linux_config" {
    for_each = var.os_profile_linux_config
    content {
      # disable_password_authentication - (optional) is a type of bool
      disable_password_authentication = os_profile_linux_config.value["disable_password_authentication"]

      dynamic "ssh_keys" {
        for_each = os_profile_linux_config.value.ssh_keys
        content {
          # key_data - (optional) is a type of string
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

  dynamic "sku" {
    for_each = var.sku
    content {
      # capacity - (required) is a type of number
      capacity = sku.value["capacity"]
      # name - (required) is a type of string
      name = sku.value["name"]
      # tier - (optional) is a type of string
      tier = sku.value["tier"]
    }
  }

  dynamic "storage_profile_data_disk" {
    for_each = var.storage_profile_data_disk
    content {
      # caching - (optional) is a type of string
      caching = storage_profile_data_disk.value["caching"]
      # create_option - (required) is a type of string
      create_option = storage_profile_data_disk.value["create_option"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = storage_profile_data_disk.value["disk_size_gb"]
      # lun - (required) is a type of number
      lun = storage_profile_data_disk.value["lun"]
      # managed_disk_type - (optional) is a type of string
      managed_disk_type = storage_profile_data_disk.value["managed_disk_type"]
    }
  }

  dynamic "storage_profile_image_reference" {
    for_each = var.storage_profile_image_reference
    content {
      # id - (optional) is a type of string
      id = storage_profile_image_reference.value["id"]
      # offer - (optional) is a type of string
      offer = storage_profile_image_reference.value["offer"]
      # publisher - (optional) is a type of string
      publisher = storage_profile_image_reference.value["publisher"]
      # sku - (optional) is a type of string
      sku = storage_profile_image_reference.value["sku"]
      # version - (optional) is a type of string
      version = storage_profile_image_reference.value["version"]
    }
  }

  dynamic "storage_profile_os_disk" {
    for_each = var.storage_profile_os_disk
    content {
      # caching - (optional) is a type of string
      caching = storage_profile_os_disk.value["caching"]
      # create_option - (required) is a type of string
      create_option = storage_profile_os_disk.value["create_option"]
      # image - (optional) is a type of string
      image = storage_profile_os_disk.value["image"]
      # managed_disk_type - (optional) is a type of string
      managed_disk_type = storage_profile_os_disk.value["managed_disk_type"]
      # name - (optional) is a type of string
      name = storage_profile_os_disk.value["name"]
      # os_type - (optional) is a type of string
      os_type = storage_profile_os_disk.value["os_type"]
      # vhd_containers - (optional) is a type of set of string
      vhd_containers = storage_profile_os_disk.value["vhd_containers"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_virtual_machine_scale_set.this.id
}

output "license_type" {
  description = "returns a string"
  value       = azurestack_virtual_machine_scale_set.this.license_type
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_virtual_machine_scale_set.this.tags
}

output "this" {
  value = azurestack_virtual_machine_scale_set.this
}
```

[top](#index)