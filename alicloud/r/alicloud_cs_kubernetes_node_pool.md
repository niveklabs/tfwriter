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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_kubernetes_node_pool" {
  source = "./modules/alicloud/r/alicloud_cs_kubernetes_node_pool"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # image_id - (optional) is a type of string
  image_id = null
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
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # system_disk_category - (optional) is a type of string
  system_disk_category = null
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # tags - (optional) is a type of map of string
  tags = {}
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
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "image_id" {
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
  cluster_id             = var.cluster_id
  image_id               = var.image_id
  instance_types         = var.instance_types
  key_name               = var.key_name
  kms_encrypted_password = var.kms_encrypted_password
  name                   = var.name
  node_count             = var.node_count
  node_name_mode         = var.node_name_mode
  password               = var.password
  security_group_id      = var.security_group_id
  system_disk_category   = var.system_disk_category
  system_disk_size       = var.system_disk_size
  tags                   = var.tags
  user_data              = var.user_data
  vswitch_ids            = var.vswitch_ids

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      auto_snapshot_policy_id = data_disks.value["auto_snapshot_policy_id"]
      category                = data_disks.value["category"]
      device                  = data_disks.value["device"]
      encrypted               = data_disks.value["encrypted"]
      kms_key_id              = data_disks.value["kms_key_id"]
      name                    = data_disks.value["name"]
      size                    = data_disks.value["size"]
      snapshot_id             = data_disks.value["snapshot_id"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "management" {
    for_each = var.management
    content {
      auto_repair      = management.value["auto_repair"]
      auto_upgrade     = management.value["auto_upgrade"]
      max_unavailable  = management.value["max_unavailable"]
      surge            = management.value["surge"]
      surge_percentage = management.value["surge_percentage"]
    }
  }

  dynamic "scaling_config" {
    for_each = var.scaling_config
    content {
      eip_bandwidth            = scaling_config.value["eip_bandwidth"]
      eip_internet_charge_type = scaling_config.value["eip_internet_charge_type"]
      is_bond_eip              = scaling_config.value["is_bond_eip"]
      max_size                 = scaling_config.value["max_size"]
      min_size                 = scaling_config.value["min_size"]
      type                     = scaling_config.value["type"]
    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      effect = taints.value["effect"]
      key    = taints.value["key"]
      value  = taints.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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