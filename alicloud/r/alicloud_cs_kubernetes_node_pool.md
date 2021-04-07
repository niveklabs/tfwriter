# alicloud_cs_kubernetes_node_pool

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_kubernetes_node_pool" {
  source = "./modules/alicloud/r/alicloud_cs_kubernetes_node_pool"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # image_id - (optional) is a type of string
  image_id = null
  # install_cloud_monitor - (optional) is a type of bool
  install_cloud_monitor = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_types - (required) is a type of list of string
  instance_types = []
  # key_name - (optional) is a type of string
  key_name = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # name - (required) is a type of string
  name = null
  # node_count - (optional) is a type of number
  node_count = null
  # node_name_mode - (optional) is a type of string
  node_name_mode = null
  # password - (optional) is a type of string
  password = null
  # period - (optional) is a type of number
  period = null
  # period_unit - (optional) is a type of string
  period_unit = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # system_disk_category - (optional) is a type of string
  system_disk_category = null
  # system_disk_performance_level - (optional) is a type of string
  system_disk_performance_level = null
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # unschedulable - (optional) is a type of bool
  unschedulable = null
  # user_data - (optional) is a type of string
  user_data = null
  # vswitch_ids - (required) is a type of list of string
  vswitch_ids = []

  data_disks = [{
    auto_snapshot_policy_id = null
    category                = null
    device                  = null
    encrypted               = null
    kms_key_id              = null
    name                    = null
    performance_level       = null
    size                    = null
    snapshot_id             = null
  }]

  labels = [{
    key   = null
    value = null
  }]

  management = [{
    auto_repair      = null
    auto_upgrade     = null
    max_unavailable  = null
    surge            = null
    surge_percentage = null
  }]

  scaling_config = [{
    eip_bandwidth            = null
    eip_internet_charge_type = null
    is_bond_eip              = null
    max_size                 = null
    min_size                 = null
    type                     = null
  }]

  taints = [{
    effect = null
    key    = null
    value  = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "install_cloud_monitor" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_types" {
  description = "(required)"
  type        = list(string)
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "node_name_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "period_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_performance_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "unschedulable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_ids" {
  description = "(required)"
  type        = list(string)
}

variable "data_disks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_snapshot_policy_id = string
      category                = string
      device                  = string
      encrypted               = string
      kms_key_id              = string
      name                    = string
      performance_level       = string
      size                    = number
      snapshot_id             = string
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "management" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_repair      = bool
      auto_upgrade     = bool
      max_unavailable  = number
      surge            = number
      surge_percentage = number
    }
  ))
  default = []
}

variable "scaling_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      eip_bandwidth            = number
      eip_internet_charge_type = string
      is_bond_eip              = bool
      max_size                 = number
      min_size                 = number
      type                     = string
    }
  ))
  default = []
}

variable "taints" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      effect = string
      key    = string
      value  = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_kubernetes_node_pool" "this" {
  # auto_renew - (optional) is a type of bool
  auto_renew = var.auto_renew
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = var.auto_renew_period
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # install_cloud_monitor - (optional) is a type of bool
  install_cloud_monitor = var.install_cloud_monitor
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_types - (required) is a type of list of string
  instance_types = var.instance_types
  # key_name - (optional) is a type of string
  key_name = var.key_name
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = var.kms_encrypted_password
  # name - (required) is a type of string
  name = var.name
  # node_count - (optional) is a type of number
  node_count = var.node_count
  # node_name_mode - (optional) is a type of string
  node_name_mode = var.node_name_mode
  # password - (optional) is a type of string
  password = var.password
  # period - (optional) is a type of number
  period = var.period
  # period_unit - (optional) is a type of string
  period_unit = var.period_unit
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # system_disk_category - (optional) is a type of string
  system_disk_category = var.system_disk_category
  # system_disk_performance_level - (optional) is a type of string
  system_disk_performance_level = var.system_disk_performance_level
  # system_disk_size - (optional) is a type of number
  system_disk_size = var.system_disk_size
  # tags - (optional) is a type of map of string
  tags = var.tags
  # unschedulable - (optional) is a type of bool
  unschedulable = var.unschedulable
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # vswitch_ids - (required) is a type of list of string
  vswitch_ids = var.vswitch_ids

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      # auto_snapshot_policy_id - (optional) is a type of string
      auto_snapshot_policy_id = data_disks.value["auto_snapshot_policy_id"]
      # category - (optional) is a type of string
      category = data_disks.value["category"]
      # device - (optional) is a type of string
      device = data_disks.value["device"]
      # encrypted - (optional) is a type of string
      encrypted = data_disks.value["encrypted"]
      # kms_key_id - (optional) is a type of string
      kms_key_id = data_disks.value["kms_key_id"]
      # name - (optional) is a type of string
      name = data_disks.value["name"]
      # performance_level - (optional) is a type of string
      performance_level = data_disks.value["performance_level"]
      # size - (optional) is a type of number
      size = data_disks.value["size"]
      # snapshot_id - (optional) is a type of string
      snapshot_id = data_disks.value["snapshot_id"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      # key - (required) is a type of string
      key = labels.value["key"]
      # value - (optional) is a type of string
      value = labels.value["value"]
    }
  }

  dynamic "management" {
    for_each = var.management
    content {
      # auto_repair - (optional) is a type of bool
      auto_repair = management.value["auto_repair"]
      # auto_upgrade - (optional) is a type of bool
      auto_upgrade = management.value["auto_upgrade"]
      # max_unavailable - (required) is a type of number
      max_unavailable = management.value["max_unavailable"]
      # surge - (optional) is a type of number
      surge = management.value["surge"]
      # surge_percentage - (optional) is a type of number
      surge_percentage = management.value["surge_percentage"]
    }
  }

  dynamic "scaling_config" {
    for_each = var.scaling_config
    content {
      # eip_bandwidth - (optional) is a type of number
      eip_bandwidth = scaling_config.value["eip_bandwidth"]
      # eip_internet_charge_type - (optional) is a type of string
      eip_internet_charge_type = scaling_config.value["eip_internet_charge_type"]
      # is_bond_eip - (optional) is a type of bool
      is_bond_eip = scaling_config.value["is_bond_eip"]
      # max_size - (required) is a type of number
      max_size = scaling_config.value["max_size"]
      # min_size - (required) is a type of number
      min_size = scaling_config.value["min_size"]
      # type - (optional) is a type of string
      type = scaling_config.value["type"]
    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      # effect - (optional) is a type of string
      effect = taints.value["effect"]
      # key - (required) is a type of string
      key = taints.value["key"]
      # value - (optional) is a type of string
      value = taints.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
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
  value       = alicloud_cs_kubernetes_node_pool.this.id
}

output "image_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_node_pool.this.image_id
}

output "node_count" {
  description = "returns a number"
  value       = alicloud_cs_kubernetes_node_pool.this.node_count
}

output "node_name_mode" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_node_pool.this.node_name_mode
}

output "scaling_group_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_node_pool.this.scaling_group_id
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_node_pool.this.security_group_id
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes_node_pool.this.vpc_id
}

output "this" {
  value = alicloud_cs_kubernetes_node_pool.this
}
```

[top](#index)