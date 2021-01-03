# azurerm_virtual_machine_scale_set

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
module "azurerm_virtual_machine_scale_set" {
  source = "./modules/azurerm/r/azurerm_virtual_machine_scale_set"

  # automatic_os_upgrade - (optional) is a type of bool
  automatic_os_upgrade = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # health_probe_id - (optional) is a type of string
  health_probe_id = null
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
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # single_placement_group - (optional) is a type of bool
  single_placement_group = null
  # tags - (optional) is a type of map of string
  tags = {}
  # upgrade_policy_mode - (required) is a type of string
  upgrade_policy_mode = null
  # zones - (optional) is a type of list of string
  zones = []

  boot_diagnostics = [{
    enabled     = null
    storage_uri = null
  }]

  extension = [{
    auto_upgrade_minor_version = null
    name                       = null
    protected_settings         = null
    provision_after_extensions = []
    publisher                  = null
    settings                   = null
    type                       = null
    type_handler_version       = null
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    type         = null
  }]

  network_profile = [{
    accelerated_networking = null
    dns_settings = [{
      dns_servers = []
    }]
    ip_configuration = [{
      application_gateway_backend_address_pool_ids = []
      application_security_group_ids               = []
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
    ip_forwarding             = null
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

  rolling_upgrade_policy = [{
    max_batch_instance_percent              = null
    max_unhealthy_instance_percent          = null
    max_unhealthy_upgraded_instance_percent = null
    pause_time_between_batches              = null
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
variable "automatic_os_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "eviction_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_probe_id" {
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

variable "proximity_placement_group_id" {
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

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
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

variable "extension" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auto_upgrade_minor_version = bool
      name                       = string
      protected_settings         = string
      provision_after_extensions = set(string)
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
      identity_ids = list(string)
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
      accelerated_networking = bool
      dns_settings = list(object(
        {
          dns_servers = list(string)
        }
      ))
      ip_configuration = list(object(
        {
          application_gateway_backend_address_pool_ids = set(string)
          application_security_group_ids               = set(string)
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
      ip_forwarding             = bool
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

variable "rolling_upgrade_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_batch_instance_percent              = number
      max_unhealthy_instance_percent          = number
      max_unhealthy_upgraded_instance_percent = number
      pause_time_between_batches              = string
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
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
resource "azurerm_virtual_machine_scale_set" "this" {
  automatic_os_upgrade         = var.automatic_os_upgrade
  eviction_policy              = var.eviction_policy
  health_probe_id              = var.health_probe_id
  license_type                 = var.license_type
  location                     = var.location
  name                         = var.name
  overprovision                = var.overprovision
  priority                     = var.priority
  proximity_placement_group_id = var.proximity_placement_group_id
  resource_group_name          = var.resource_group_name
  single_placement_group       = var.single_placement_group
  tags                         = var.tags
  upgrade_policy_mode          = var.upgrade_policy_mode
  zones                        = var.zones

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      enabled     = boot_diagnostics.value["enabled"]
      storage_uri = boot_diagnostics.value["storage_uri"]
    }
  }

  dynamic "extension" {
    for_each = var.extension
    content {
      auto_upgrade_minor_version = extension.value["auto_upgrade_minor_version"]
      name                       = extension.value["name"]
      protected_settings         = extension.value["protected_settings"]
      provision_after_extensions = extension.value["provision_after_extensions"]
      publisher                  = extension.value["publisher"]
      settings                   = extension.value["settings"]
      type                       = extension.value["type"]
      type_handler_version       = extension.value["type_handler_version"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      identity_ids = identity.value["identity_ids"]
      type         = identity.value["type"]
    }
  }

  dynamic "network_profile" {
    for_each = var.network_profile
    content {
      accelerated_networking    = network_profile.value["accelerated_networking"]
      ip_forwarding             = network_profile.value["ip_forwarding"]
      name                      = network_profile.value["name"]
      network_security_group_id = network_profile.value["network_security_group_id"]
      primary                   = network_profile.value["primary"]

      dynamic "dns_settings" {
        for_each = network_profile.value.dns_settings
        content {
          dns_servers = dns_settings.value["dns_servers"]
        }
      }

      dynamic "ip_configuration" {
        for_each = network_profile.value.ip_configuration
        content {
          application_gateway_backend_address_pool_ids = ip_configuration.value["application_gateway_backend_address_pool_ids"]
          application_security_group_ids               = ip_configuration.value["application_security_group_ids"]
          load_balancer_backend_address_pool_ids       = ip_configuration.value["load_balancer_backend_address_pool_ids"]
          load_balancer_inbound_nat_rules_ids          = ip_configuration.value["load_balancer_inbound_nat_rules_ids"]
          name                                         = ip_configuration.value["name"]
          primary                                      = ip_configuration.value["primary"]
          subnet_id                                    = ip_configuration.value["subnet_id"]

          dynamic "public_ip_address_configuration" {
            for_each = ip_configuration.value.public_ip_address_configuration
            content {
              domain_name_label = public_ip_address_configuration.value["domain_name_label"]
              idle_timeout      = public_ip_address_configuration.value["idle_timeout"]
              name              = public_ip_address_configuration.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "os_profile" {
    for_each = var.os_profile
    content {
      admin_password       = os_profile.value["admin_password"]
      admin_username       = os_profile.value["admin_username"]
      computer_name_prefix = os_profile.value["computer_name_prefix"]
      custom_data          = os_profile.value["custom_data"]
    }
  }

  dynamic "os_profile_linux_config" {
    for_each = var.os_profile_linux_config
    content {
      disable_password_authentication = os_profile_linux_config.value["disable_password_authentication"]

      dynamic "ssh_keys" {
        for_each = os_profile_linux_config.value.ssh_keys
        content {
          key_data = ssh_keys.value["key_data"]
          path     = ssh_keys.value["path"]
        }
      }

    }
  }

  dynamic "os_profile_secrets" {
    for_each = var.os_profile_secrets
    content {
      source_vault_id = os_profile_secrets.value["source_vault_id"]

      dynamic "vault_certificates" {
        for_each = os_profile_secrets.value.vault_certificates
        content {
          certificate_store = vault_certificates.value["certificate_store"]
          certificate_url   = vault_certificates.value["certificate_url"]
        }
      }

    }
  }

  dynamic "os_profile_windows_config" {
    for_each = var.os_profile_windows_config
    content {
      enable_automatic_upgrades = os_profile_windows_config.value["enable_automatic_upgrades"]
      provision_vm_agent        = os_profile_windows_config.value["provision_vm_agent"]

      dynamic "additional_unattend_config" {
        for_each = os_profile_windows_config.value.additional_unattend_config
        content {
          component    = additional_unattend_config.value["component"]
          content      = additional_unattend_config.value["content"]
          pass         = additional_unattend_config.value["pass"]
          setting_name = additional_unattend_config.value["setting_name"]
        }
      }

      dynamic "winrm" {
        for_each = os_profile_windows_config.value.winrm
        content {
          certificate_url = winrm.value["certificate_url"]
          protocol        = winrm.value["protocol"]
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

  dynamic "rolling_upgrade_policy" {
    for_each = var.rolling_upgrade_policy
    content {
      max_batch_instance_percent              = rolling_upgrade_policy.value["max_batch_instance_percent"]
      max_unhealthy_instance_percent          = rolling_upgrade_policy.value["max_unhealthy_instance_percent"]
      max_unhealthy_upgraded_instance_percent = rolling_upgrade_policy.value["max_unhealthy_upgraded_instance_percent"]
      pause_time_between_batches              = rolling_upgrade_policy.value["pause_time_between_batches"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      capacity = sku.value["capacity"]
      name     = sku.value["name"]
      tier     = sku.value["tier"]
    }
  }

  dynamic "storage_profile_data_disk" {
    for_each = var.storage_profile_data_disk
    content {
      caching           = storage_profile_data_disk.value["caching"]
      create_option     = storage_profile_data_disk.value["create_option"]
      disk_size_gb      = storage_profile_data_disk.value["disk_size_gb"]
      lun               = storage_profile_data_disk.value["lun"]
      managed_disk_type = storage_profile_data_disk.value["managed_disk_type"]
    }
  }

  dynamic "storage_profile_image_reference" {
    for_each = var.storage_profile_image_reference
    content {
      id        = storage_profile_image_reference.value["id"]
      offer     = storage_profile_image_reference.value["offer"]
      publisher = storage_profile_image_reference.value["publisher"]
      sku       = storage_profile_image_reference.value["sku"]
      version   = storage_profile_image_reference.value["version"]
    }
  }

  dynamic "storage_profile_os_disk" {
    for_each = var.storage_profile_os_disk
    content {
      caching           = storage_profile_os_disk.value["caching"]
      create_option     = storage_profile_os_disk.value["create_option"]
      image             = storage_profile_os_disk.value["image"]
      managed_disk_type = storage_profile_os_disk.value["managed_disk_type"]
      name              = storage_profile_os_disk.value["name"]
      os_type           = storage_profile_os_disk.value["os_type"]
      vhd_containers    = storage_profile_os_disk.value["vhd_containers"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_virtual_machine_scale_set.this.id
}

output "license_type" {
  description = "returns a string"
  value       = azurerm_virtual_machine_scale_set.this.license_type
}

output "this" {
  value = azurerm_virtual_machine_scale_set.this
}
```

[top](#index)