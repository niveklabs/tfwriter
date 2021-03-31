# azurerm_windows_virtual_machine_scale_set

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_windows_virtual_machine_scale_set" {
  source = "./modules/azurerm/r/azurerm_windows_virtual_machine_scale_set"

  # admin_password - (required) is a type of string
  admin_password = null
  # admin_username - (required) is a type of string
  admin_username = null
  # computer_name_prefix - (optional) is a type of string
  computer_name_prefix = null
  # custom_data - (optional) is a type of string
  custom_data = null
  # do_not_run_extensions_on_overprovisioned_machines - (optional) is a type of bool
  do_not_run_extensions_on_overprovisioned_machines = null
  # enable_automatic_updates - (optional) is a type of bool
  enable_automatic_updates = null
  # encryption_at_host_enabled - (optional) is a type of bool
  encryption_at_host_enabled = null
  # eviction_policy - (optional) is a type of string
  eviction_policy = null
  # extensions_time_budget - (optional) is a type of string
  extensions_time_budget = null
  # health_probe_id - (optional) is a type of string
  health_probe_id = null
  # instances - (required) is a type of number
  instances = null
  # license_type - (optional) is a type of string
  license_type = null
  # location - (required) is a type of string
  location = null
  # max_bid_price - (optional) is a type of number
  max_bid_price = null
  # name - (required) is a type of string
  name = null
  # overprovision - (optional) is a type of bool
  overprovision = null
  # platform_fault_domain_count - (optional) is a type of number
  platform_fault_domain_count = null
  # priority - (optional) is a type of string
  priority = null
  # provision_vm_agent - (optional) is a type of bool
  provision_vm_agent = null
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scale_in_policy - (optional) is a type of string
  scale_in_policy = null
  # single_placement_group - (optional) is a type of bool
  single_placement_group = null
  # sku - (required) is a type of string
  sku = null
  # source_image_id - (optional) is a type of string
  source_image_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timezone - (optional) is a type of string
  timezone = null
  # upgrade_mode - (optional) is a type of string
  upgrade_mode = null
  # zone_balance - (optional) is a type of bool
  zone_balance = null
  # zones - (optional) is a type of list of string
  zones = []

  additional_capabilities = [{
    ultra_ssd_enabled = null
  }]

  additional_unattend_content = [{
    content = null
    setting = null
  }]

  automatic_instance_repair = [{
    enabled      = null
    grace_period = null
  }]

  automatic_os_upgrade_policy = [{
    disable_automatic_rollback  = null
    enable_automatic_os_upgrade = null
  }]

  boot_diagnostics = [{
    storage_account_uri = null
  }]

  data_disk = [{
    caching                   = null
    create_option             = null
    disk_encryption_set_id    = null
    disk_iops_read_write      = null
    disk_mbps_read_write      = null
    disk_size_gb              = null
    lun                       = null
    storage_account_type      = null
    write_accelerator_enabled = null
  }]

  extension = [{
    auto_upgrade_minor_version = null
    force_update_tag           = null
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

  network_interface = [{
    dns_servers                   = []
    enable_accelerated_networking = null
    enable_ip_forwarding          = null
    ip_configuration = [{
      application_gateway_backend_address_pool_ids = []
      application_security_group_ids               = []
      load_balancer_backend_address_pool_ids       = []
      load_balancer_inbound_nat_rules_ids          = []
      name                                         = null
      primary                                      = null
      public_ip_address = [{
        domain_name_label       = null
        idle_timeout_in_minutes = null
        ip_tag = [{
          tag  = null
          type = null
        }]
        name                = null
        public_ip_prefix_id = null
      }]
      subnet_id = null
      version   = null
    }]
    name                      = null
    network_security_group_id = null
    primary                   = null
  }]

  os_disk = [{
    caching = null
    diff_disk_settings = [{
      option = null
    }]
    disk_encryption_set_id    = null
    disk_size_gb              = null
    storage_account_type      = null
    write_accelerator_enabled = null
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

  terminate_notification = [{
    enabled = null
    timeout = null
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

variable "computer_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "do_not_run_extensions_on_overprovisioned_machines" {
  description = "(optional)"
  type        = bool
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

variable "health_probe_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instances" {
  description = "(required)"
  type        = number
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

variable "overprovision" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "platform_fault_domain_count" {
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

variable "scale_in_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_placement_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sku" {
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

variable "upgrade_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_balance" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "automatic_instance_repair" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled      = bool
      grace_period = string
    }
  ))
  default = []
}

variable "automatic_os_upgrade_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable_automatic_rollback  = bool
      enable_automatic_os_upgrade = bool
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

variable "data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      caching                   = string
      create_option             = string
      disk_encryption_set_id    = string
      disk_iops_read_write      = number
      disk_mbps_read_write      = number
      disk_size_gb              = number
      lun                       = number
      storage_account_type      = string
      write_accelerator_enabled = bool
    }
  ))
  default = []
}

variable "extension" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_upgrade_minor_version = bool
      force_update_tag           = string
      name                       = string
      protected_settings         = string
      provision_after_extensions = list(string)
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
      identity_ids = set(string)
      principal_id = string
      type         = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      dns_servers                   = list(string)
      enable_accelerated_networking = bool
      enable_ip_forwarding          = bool
      ip_configuration = list(object(
        {
          application_gateway_backend_address_pool_ids = set(string)
          application_security_group_ids               = set(string)
          load_balancer_backend_address_pool_ids       = set(string)
          load_balancer_inbound_nat_rules_ids          = set(string)
          name                                         = string
          primary                                      = bool
          public_ip_address = list(object(
            {
              domain_name_label       = string
              idle_timeout_in_minutes = number
              ip_tag = list(object(
                {
                  tag  = string
                  type = string
                }
              ))
              name                = string
              public_ip_prefix_id = string
            }
          ))
          subnet_id = string
          version   = string
        }
      ))
      name                      = string
      network_security_group_id = string
      primary                   = bool
    }
  ))
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

variable "terminate_notification" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      timeout = string
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
resource "azurerm_windows_virtual_machine_scale_set" "this" {
  admin_password                                    = var.admin_password
  admin_username                                    = var.admin_username
  computer_name_prefix                              = var.computer_name_prefix
  custom_data                                       = var.custom_data
  do_not_run_extensions_on_overprovisioned_machines = var.do_not_run_extensions_on_overprovisioned_machines
  enable_automatic_updates                          = var.enable_automatic_updates
  encryption_at_host_enabled                        = var.encryption_at_host_enabled
  eviction_policy                                   = var.eviction_policy
  extensions_time_budget                            = var.extensions_time_budget
  health_probe_id                                   = var.health_probe_id
  instances                                         = var.instances
  license_type                                      = var.license_type
  location                                          = var.location
  max_bid_price                                     = var.max_bid_price
  name                                              = var.name
  overprovision                                     = var.overprovision
  platform_fault_domain_count                       = var.platform_fault_domain_count
  priority                                          = var.priority
  provision_vm_agent                                = var.provision_vm_agent
  proximity_placement_group_id                      = var.proximity_placement_group_id
  resource_group_name                               = var.resource_group_name
  scale_in_policy                                   = var.scale_in_policy
  single_placement_group                            = var.single_placement_group
  sku                                               = var.sku
  source_image_id                                   = var.source_image_id
  tags                                              = var.tags
  timezone                                          = var.timezone
  upgrade_mode                                      = var.upgrade_mode
  zone_balance                                      = var.zone_balance
  zones                                             = var.zones

  dynamic "additional_capabilities" {
    for_each = var.additional_capabilities
    content {
      ultra_ssd_enabled = additional_capabilities.value["ultra_ssd_enabled"]
    }
  }

  dynamic "additional_unattend_content" {
    for_each = var.additional_unattend_content
    content {
      content = additional_unattend_content.value["content"]
      setting = additional_unattend_content.value["setting"]
    }
  }

  dynamic "automatic_instance_repair" {
    for_each = var.automatic_instance_repair
    content {
      enabled      = automatic_instance_repair.value["enabled"]
      grace_period = automatic_instance_repair.value["grace_period"]
    }
  }

  dynamic "automatic_os_upgrade_policy" {
    for_each = var.automatic_os_upgrade_policy
    content {
      disable_automatic_rollback  = automatic_os_upgrade_policy.value["disable_automatic_rollback"]
      enable_automatic_os_upgrade = automatic_os_upgrade_policy.value["enable_automatic_os_upgrade"]
    }
  }

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      storage_account_uri = boot_diagnostics.value["storage_account_uri"]
    }
  }

  dynamic "data_disk" {
    for_each = var.data_disk
    content {
      caching                   = data_disk.value["caching"]
      create_option             = data_disk.value["create_option"]
      disk_encryption_set_id    = data_disk.value["disk_encryption_set_id"]
      disk_iops_read_write      = data_disk.value["disk_iops_read_write"]
      disk_mbps_read_write      = data_disk.value["disk_mbps_read_write"]
      disk_size_gb              = data_disk.value["disk_size_gb"]
      lun                       = data_disk.value["lun"]
      storage_account_type      = data_disk.value["storage_account_type"]
      write_accelerator_enabled = data_disk.value["write_accelerator_enabled"]
    }
  }

  dynamic "extension" {
    for_each = var.extension
    content {
      auto_upgrade_minor_version = extension.value["auto_upgrade_minor_version"]
      force_update_tag           = extension.value["force_update_tag"]
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

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      dns_servers                   = network_interface.value["dns_servers"]
      enable_accelerated_networking = network_interface.value["enable_accelerated_networking"]
      enable_ip_forwarding          = network_interface.value["enable_ip_forwarding"]
      name                          = network_interface.value["name"]
      network_security_group_id     = network_interface.value["network_security_group_id"]
      primary                       = network_interface.value["primary"]

      dynamic "ip_configuration" {
        for_each = network_interface.value.ip_configuration
        content {
          application_gateway_backend_address_pool_ids = ip_configuration.value["application_gateway_backend_address_pool_ids"]
          application_security_group_ids               = ip_configuration.value["application_security_group_ids"]
          load_balancer_backend_address_pool_ids       = ip_configuration.value["load_balancer_backend_address_pool_ids"]
          load_balancer_inbound_nat_rules_ids          = ip_configuration.value["load_balancer_inbound_nat_rules_ids"]
          name                                         = ip_configuration.value["name"]
          primary                                      = ip_configuration.value["primary"]
          subnet_id                                    = ip_configuration.value["subnet_id"]
          version                                      = ip_configuration.value["version"]

          dynamic "public_ip_address" {
            for_each = ip_configuration.value.public_ip_address
            content {
              domain_name_label       = public_ip_address.value["domain_name_label"]
              idle_timeout_in_minutes = public_ip_address.value["idle_timeout_in_minutes"]
              name                    = public_ip_address.value["name"]
              public_ip_prefix_id     = public_ip_address.value["public_ip_prefix_id"]

              dynamic "ip_tag" {
                for_each = public_ip_address.value.ip_tag
                content {
                  tag  = ip_tag.value["tag"]
                  type = ip_tag.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "os_disk" {
    for_each = var.os_disk
    content {
      caching                   = os_disk.value["caching"]
      disk_encryption_set_id    = os_disk.value["disk_encryption_set_id"]
      disk_size_gb              = os_disk.value["disk_size_gb"]
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

  dynamic "rolling_upgrade_policy" {
    for_each = var.rolling_upgrade_policy
    content {
      max_batch_instance_percent              = rolling_upgrade_policy.value["max_batch_instance_percent"]
      max_unhealthy_instance_percent          = rolling_upgrade_policy.value["max_unhealthy_instance_percent"]
      max_unhealthy_upgraded_instance_percent = rolling_upgrade_policy.value["max_unhealthy_upgraded_instance_percent"]
      pause_time_between_batches              = rolling_upgrade_policy.value["pause_time_between_batches"]
    }
  }

  dynamic "secret" {
    for_each = var.secret
    content {
      key_vault_id = secret.value["key_vault_id"]

      dynamic "certificate" {
        for_each = secret.value.certificate
        content {
          store = certificate.value["store"]
          url   = certificate.value["url"]
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

  dynamic "terminate_notification" {
    for_each = var.terminate_notification
    content {
      enabled = terminate_notification.value["enabled"]
      timeout = terminate_notification.value["timeout"]
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

  dynamic "winrm_listener" {
    for_each = var.winrm_listener
    content {
      certificate_url = winrm_listener.value["certificate_url"]
      protocol        = winrm_listener.value["protocol"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "computer_name_prefix" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine_scale_set.this.computer_name_prefix
}

output "id" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine_scale_set.this.id
}

output "platform_fault_domain_count" {
  description = "returns a number"
  value       = azurerm_windows_virtual_machine_scale_set.this.platform_fault_domain_count
}

output "unique_id" {
  description = "returns a string"
  value       = azurerm_windows_virtual_machine_scale_set.this.unique_id
}

output "this" {
  value = azurerm_windows_virtual_machine_scale_set.this
}
```

[top](#index)