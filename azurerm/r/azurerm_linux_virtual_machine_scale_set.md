# azurerm_linux_virtual_machine_scale_set

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
module "azurerm_linux_virtual_machine_scale_set" {
  source = "./modules/azurerm/r/azurerm_linux_virtual_machine_scale_set"

  # admin_password - (optional) is a type of string
  admin_password = null
  # admin_username - (required) is a type of string
  admin_username = null
  # computer_name_prefix - (optional) is a type of string
  computer_name_prefix = null
  # custom_data - (optional) is a type of string
  custom_data = null
  # disable_password_authentication - (optional) is a type of bool
  disable_password_authentication = null
  # do_not_run_extensions_on_overprovisioned_machines - (optional) is a type of bool
  do_not_run_extensions_on_overprovisioned_machines = null
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
  # upgrade_mode - (optional) is a type of string
  upgrade_mode = null
  # zone_balance - (optional) is a type of bool
  zone_balance = null
  # zones - (optional) is a type of list of string
  zones = []

  additional_capabilities = [{
    ultra_ssd_enabled = null
  }]

  admin_ssh_key = [{
    public_key = null
    username   = null
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

variable "disable_password_authentication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "do_not_run_extensions_on_overprovisioned_machines" {
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
```

[top](#index)

### Resource

```terraform
resource "azurerm_linux_virtual_machine_scale_set" "this" {
  # admin_password - (optional) is a type of string
  admin_password = var.admin_password
  # admin_username - (required) is a type of string
  admin_username = var.admin_username
  # computer_name_prefix - (optional) is a type of string
  computer_name_prefix = var.computer_name_prefix
  # custom_data - (optional) is a type of string
  custom_data = var.custom_data
  # disable_password_authentication - (optional) is a type of bool
  disable_password_authentication = var.disable_password_authentication
  # do_not_run_extensions_on_overprovisioned_machines - (optional) is a type of bool
  do_not_run_extensions_on_overprovisioned_machines = var.do_not_run_extensions_on_overprovisioned_machines
  # encryption_at_host_enabled - (optional) is a type of bool
  encryption_at_host_enabled = var.encryption_at_host_enabled
  # eviction_policy - (optional) is a type of string
  eviction_policy = var.eviction_policy
  # extensions_time_budget - (optional) is a type of string
  extensions_time_budget = var.extensions_time_budget
  # health_probe_id - (optional) is a type of string
  health_probe_id = var.health_probe_id
  # instances - (required) is a type of number
  instances = var.instances
  # location - (required) is a type of string
  location = var.location
  # max_bid_price - (optional) is a type of number
  max_bid_price = var.max_bid_price
  # name - (required) is a type of string
  name = var.name
  # overprovision - (optional) is a type of bool
  overprovision = var.overprovision
  # platform_fault_domain_count - (optional) is a type of number
  platform_fault_domain_count = var.platform_fault_domain_count
  # priority - (optional) is a type of string
  priority = var.priority
  # provision_vm_agent - (optional) is a type of bool
  provision_vm_agent = var.provision_vm_agent
  # proximity_placement_group_id - (optional) is a type of string
  proximity_placement_group_id = var.proximity_placement_group_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # scale_in_policy - (optional) is a type of string
  scale_in_policy = var.scale_in_policy
  # single_placement_group - (optional) is a type of bool
  single_placement_group = var.single_placement_group
  # sku - (required) is a type of string
  sku = var.sku
  # source_image_id - (optional) is a type of string
  source_image_id = var.source_image_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # upgrade_mode - (optional) is a type of string
  upgrade_mode = var.upgrade_mode
  # zone_balance - (optional) is a type of bool
  zone_balance = var.zone_balance
  # zones - (optional) is a type of list of string
  zones = var.zones

  dynamic "additional_capabilities" {
    for_each = var.additional_capabilities
    content {
      # ultra_ssd_enabled - (optional) is a type of bool
      ultra_ssd_enabled = additional_capabilities.value["ultra_ssd_enabled"]
    }
  }

  dynamic "admin_ssh_key" {
    for_each = var.admin_ssh_key
    content {
      # public_key - (required) is a type of string
      public_key = admin_ssh_key.value["public_key"]
      # username - (required) is a type of string
      username = admin_ssh_key.value["username"]
    }
  }

  dynamic "automatic_instance_repair" {
    for_each = var.automatic_instance_repair
    content {
      # enabled - (required) is a type of bool
      enabled = automatic_instance_repair.value["enabled"]
      # grace_period - (optional) is a type of string
      grace_period = automatic_instance_repair.value["grace_period"]
    }
  }

  dynamic "automatic_os_upgrade_policy" {
    for_each = var.automatic_os_upgrade_policy
    content {
      # disable_automatic_rollback - (required) is a type of bool
      disable_automatic_rollback = automatic_os_upgrade_policy.value["disable_automatic_rollback"]
      # enable_automatic_os_upgrade - (required) is a type of bool
      enable_automatic_os_upgrade = automatic_os_upgrade_policy.value["enable_automatic_os_upgrade"]
    }
  }

  dynamic "boot_diagnostics" {
    for_each = var.boot_diagnostics
    content {
      # storage_account_uri - (optional) is a type of string
      storage_account_uri = boot_diagnostics.value["storage_account_uri"]
    }
  }

  dynamic "data_disk" {
    for_each = var.data_disk
    content {
      # caching - (required) is a type of string
      caching = data_disk.value["caching"]
      # create_option - (optional) is a type of string
      create_option = data_disk.value["create_option"]
      # disk_encryption_set_id - (optional) is a type of string
      disk_encryption_set_id = data_disk.value["disk_encryption_set_id"]
      # disk_iops_read_write - (optional) is a type of number
      disk_iops_read_write = data_disk.value["disk_iops_read_write"]
      # disk_mbps_read_write - (optional) is a type of number
      disk_mbps_read_write = data_disk.value["disk_mbps_read_write"]
      # disk_size_gb - (required) is a type of number
      disk_size_gb = data_disk.value["disk_size_gb"]
      # lun - (required) is a type of number
      lun = data_disk.value["lun"]
      # storage_account_type - (required) is a type of string
      storage_account_type = data_disk.value["storage_account_type"]
      # write_accelerator_enabled - (optional) is a type of bool
      write_accelerator_enabled = data_disk.value["write_accelerator_enabled"]
    }
  }

  dynamic "extension" {
    for_each = var.extension
    content {
      # auto_upgrade_minor_version - (optional) is a type of bool
      auto_upgrade_minor_version = extension.value["auto_upgrade_minor_version"]
      # force_update_tag - (optional) is a type of string
      force_update_tag = extension.value["force_update_tag"]
      # name - (required) is a type of string
      name = extension.value["name"]
      # protected_settings - (optional) is a type of string
      protected_settings = extension.value["protected_settings"]
      # provision_after_extensions - (optional) is a type of list of string
      provision_after_extensions = extension.value["provision_after_extensions"]
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
      # identity_ids - (optional) is a type of set of string
      identity_ids = identity.value["identity_ids"]
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      # dns_servers - (optional) is a type of list of string
      dns_servers = network_interface.value["dns_servers"]
      # enable_accelerated_networking - (optional) is a type of bool
      enable_accelerated_networking = network_interface.value["enable_accelerated_networking"]
      # enable_ip_forwarding - (optional) is a type of bool
      enable_ip_forwarding = network_interface.value["enable_ip_forwarding"]
      # name - (required) is a type of string
      name = network_interface.value["name"]
      # network_security_group_id - (optional) is a type of string
      network_security_group_id = network_interface.value["network_security_group_id"]
      # primary - (optional) is a type of bool
      primary = network_interface.value["primary"]

      dynamic "ip_configuration" {
        for_each = network_interface.value.ip_configuration
        content {
          # application_gateway_backend_address_pool_ids - (optional) is a type of set of string
          application_gateway_backend_address_pool_ids = ip_configuration.value["application_gateway_backend_address_pool_ids"]
          # application_security_group_ids - (optional) is a type of set of string
          application_security_group_ids = ip_configuration.value["application_security_group_ids"]
          # load_balancer_backend_address_pool_ids - (optional) is a type of set of string
          load_balancer_backend_address_pool_ids = ip_configuration.value["load_balancer_backend_address_pool_ids"]
          # load_balancer_inbound_nat_rules_ids - (optional) is a type of set of string
          load_balancer_inbound_nat_rules_ids = ip_configuration.value["load_balancer_inbound_nat_rules_ids"]
          # name - (required) is a type of string
          name = ip_configuration.value["name"]
          # primary - (optional) is a type of bool
          primary = ip_configuration.value["primary"]
          # subnet_id - (optional) is a type of string
          subnet_id = ip_configuration.value["subnet_id"]
          # version - (optional) is a type of string
          version = ip_configuration.value["version"]

          dynamic "public_ip_address" {
            for_each = ip_configuration.value.public_ip_address
            content {
              # domain_name_label - (optional) is a type of string
              domain_name_label = public_ip_address.value["domain_name_label"]
              # idle_timeout_in_minutes - (optional) is a type of number
              idle_timeout_in_minutes = public_ip_address.value["idle_timeout_in_minutes"]
              # name - (required) is a type of string
              name = public_ip_address.value["name"]
              # public_ip_prefix_id - (optional) is a type of string
              public_ip_prefix_id = public_ip_address.value["public_ip_prefix_id"]

              dynamic "ip_tag" {
                for_each = public_ip_address.value.ip_tag
                content {
                  # tag - (required) is a type of string
                  tag = ip_tag.value["tag"]
                  # type - (required) is a type of string
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
      # caching - (required) is a type of string
      caching = os_disk.value["caching"]
      # disk_encryption_set_id - (optional) is a type of string
      disk_encryption_set_id = os_disk.value["disk_encryption_set_id"]
      # disk_size_gb - (optional) is a type of number
      disk_size_gb = os_disk.value["disk_size_gb"]
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

  dynamic "rolling_upgrade_policy" {
    for_each = var.rolling_upgrade_policy
    content {
      # max_batch_instance_percent - (required) is a type of number
      max_batch_instance_percent = rolling_upgrade_policy.value["max_batch_instance_percent"]
      # max_unhealthy_instance_percent - (required) is a type of number
      max_unhealthy_instance_percent = rolling_upgrade_policy.value["max_unhealthy_instance_percent"]
      # max_unhealthy_upgraded_instance_percent - (required) is a type of number
      max_unhealthy_upgraded_instance_percent = rolling_upgrade_policy.value["max_unhealthy_upgraded_instance_percent"]
      # pause_time_between_batches - (required) is a type of string
      pause_time_between_batches = rolling_upgrade_policy.value["pause_time_between_batches"]
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

  dynamic "terminate_notification" {
    for_each = var.terminate_notification
    content {
      # enabled - (required) is a type of bool
      enabled = terminate_notification.value["enabled"]
      # timeout - (optional) is a type of string
      timeout = terminate_notification.value["timeout"]
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
output "computer_name_prefix" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine_scale_set.this.computer_name_prefix
}

output "id" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine_scale_set.this.id
}

output "platform_fault_domain_count" {
  description = "returns a number"
  value       = azurerm_linux_virtual_machine_scale_set.this.platform_fault_domain_count
}

output "unique_id" {
  description = "returns a string"
  value       = azurerm_linux_virtual_machine_scale_set.this.unique_id
}

output "this" {
  value = azurerm_linux_virtual_machine_scale_set.this
}
```

[top](#index)