# azurerm_netapp_volume

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
module "azurerm_netapp_volume" {
  source = "./modules/azurerm/r/azurerm_netapp_volume"

  # account_name - (required) is a type of string
  account_name = null
  # create_from_snapshot_resource_id - (optional) is a type of string
  create_from_snapshot_resource_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # pool_name - (required) is a type of string
  pool_name = null
  # protocols - (optional) is a type of set of string
  protocols = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_level - (required) is a type of string
  service_level = null
  # storage_quota_in_gb - (required) is a type of number
  storage_quota_in_gb = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # volume_path - (required) is a type of string
  volume_path = null

  data_protection_replication = [{
    endpoint_type             = null
    remote_volume_location    = null
    remote_volume_resource_id = null
    replication_frequency     = null
  }]

  export_policy_rule = [{
    allowed_clients   = []
    cifs_enabled      = null
    nfsv3_enabled     = null
    nfsv4_enabled     = null
    protocols_enabled = []
    rule_index        = null
    unix_read_only    = null
    unix_read_write   = null
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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "create_from_snapshot_resource_id" {
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

variable "pool_name" {
  description = "(required)"
  type        = string
}

variable "protocols" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_level" {
  description = "(required)"
  type        = string
}

variable "storage_quota_in_gb" {
  description = "(required)"
  type        = number
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "volume_path" {
  description = "(required)"
  type        = string
}

variable "data_protection_replication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint_type             = string
      remote_volume_location    = string
      remote_volume_resource_id = string
      replication_frequency     = string
    }
  ))
  default = []
}

variable "export_policy_rule" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      allowed_clients   = set(string)
      cifs_enabled      = bool
      nfsv3_enabled     = bool
      nfsv4_enabled     = bool
      protocols_enabled = list(string)
      rule_index        = number
      unix_read_only    = bool
      unix_read_write   = bool
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
resource "azurerm_netapp_volume" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # create_from_snapshot_resource_id - (optional) is a type of string
  create_from_snapshot_resource_id = var.create_from_snapshot_resource_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # pool_name - (required) is a type of string
  pool_name = var.pool_name
  # protocols - (optional) is a type of set of string
  protocols = var.protocols
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # service_level - (required) is a type of string
  service_level = var.service_level
  # storage_quota_in_gb - (required) is a type of number
  storage_quota_in_gb = var.storage_quota_in_gb
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # volume_path - (required) is a type of string
  volume_path = var.volume_path

  dynamic "data_protection_replication" {
    for_each = var.data_protection_replication
    content {
      # endpoint_type - (optional) is a type of string
      endpoint_type = data_protection_replication.value["endpoint_type"]
      # remote_volume_location - (required) is a type of string
      remote_volume_location = data_protection_replication.value["remote_volume_location"]
      # remote_volume_resource_id - (required) is a type of string
      remote_volume_resource_id = data_protection_replication.value["remote_volume_resource_id"]
      # replication_frequency - (required) is a type of string
      replication_frequency = data_protection_replication.value["replication_frequency"]
    }
  }

  dynamic "export_policy_rule" {
    for_each = var.export_policy_rule
    content {
      # allowed_clients - (required) is a type of set of string
      allowed_clients = export_policy_rule.value["allowed_clients"]
      # cifs_enabled - (optional) is a type of bool
      cifs_enabled = export_policy_rule.value["cifs_enabled"]
      # nfsv3_enabled - (optional) is a type of bool
      nfsv3_enabled = export_policy_rule.value["nfsv3_enabled"]
      # nfsv4_enabled - (optional) is a type of bool
      nfsv4_enabled = export_policy_rule.value["nfsv4_enabled"]
      # protocols_enabled - (optional) is a type of list of string
      protocols_enabled = export_policy_rule.value["protocols_enabled"]
      # rule_index - (required) is a type of number
      rule_index = export_policy_rule.value["rule_index"]
      # unix_read_only - (optional) is a type of bool
      unix_read_only = export_policy_rule.value["unix_read_only"]
      # unix_read_write - (optional) is a type of bool
      unix_read_write = export_policy_rule.value["unix_read_write"]
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
output "create_from_snapshot_resource_id" {
  description = "returns a string"
  value       = azurerm_netapp_volume.this.create_from_snapshot_resource_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_netapp_volume.this.id
}

output "mount_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_netapp_volume.this.mount_ip_addresses
}

output "protocols" {
  description = "returns a set of string"
  value       = azurerm_netapp_volume.this.protocols
}

output "this" {
  value = azurerm_netapp_volume.this
}
```

[top](#index)