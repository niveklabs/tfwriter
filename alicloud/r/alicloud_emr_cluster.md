# alicloud_emr_cluster

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
module "alicloud_emr_cluster" {
  source = "./modules/alicloud/r/alicloud_emr_cluster"

  # charge_type - (optional) is a type of string
  charge_type = null
  # cluster_type - (required) is a type of string
  cluster_type = null
  # deposit_type - (optional) is a type of string
  deposit_type = null
  # eas_enable - (optional) is a type of bool
  eas_enable = null
  # emr_ver - (required) is a type of string
  emr_ver = null
  # high_availability_enable - (optional) is a type of bool
  high_availability_enable = null
  # is_open_public_ip - (optional) is a type of bool
  is_open_public_ip = null
  # key_pair_name - (optional) is a type of string
  key_pair_name = null
  # master_pwd - (optional) is a type of string
  master_pwd = null
  # name - (required) is a type of string
  name = null
  # option_software_list - (optional) is a type of list of string
  option_software_list = []
  # period - (optional) is a type of number
  period = null
  # related_cluster_id - (optional) is a type of string
  related_cluster_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # ssh_enable - (optional) is a type of bool
  ssh_enable = null
  # tags - (optional) is a type of map of string
  tags = {}
  # use_local_metadb - (optional) is a type of bool
  use_local_metadb = null
  # user_defined_emr_ecs_role - (optional) is a type of string
  user_defined_emr_ecs_role = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (required) is a type of string
  zone_id = null

  bootstrap_action = [{
    arg  = null
    name = null
    path = null
  }]

  host_group = [{
    auto_renew        = null
    charge_type       = null
    disk_capacity     = null
    disk_count        = null
    disk_type         = null
    gpu_driver        = null
    host_group_name   = null
    host_group_type   = null
    instance_list     = null
    instance_type     = null
    node_count        = null
    period            = null
    sys_disk_capacity = null
    sys_disk_type     = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_type" {
  description = "(required)"
  type        = string
}

variable "deposit_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eas_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "emr_ver" {
  description = "(required)"
  type        = string
}

variable "high_availability_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_open_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_pair_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "option_software_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "related_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "use_local_metadb" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_defined_emr_ecs_role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "bootstrap_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      arg  = string
      name = string
      path = string
    }
  ))
  default = []
}

variable "host_group" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auto_renew        = bool
      charge_type       = string
      disk_capacity     = string
      disk_count        = string
      disk_type         = string
      gpu_driver        = string
      host_group_name   = string
      host_group_type   = string
      instance_list     = string
      instance_type     = string
      node_count        = string
      period            = number
      sys_disk_capacity = string
      sys_disk_type     = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_emr_cluster" "this" {
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # cluster_type - (required) is a type of string
  cluster_type = var.cluster_type
  # deposit_type - (optional) is a type of string
  deposit_type = var.deposit_type
  # eas_enable - (optional) is a type of bool
  eas_enable = var.eas_enable
  # emr_ver - (required) is a type of string
  emr_ver = var.emr_ver
  # high_availability_enable - (optional) is a type of bool
  high_availability_enable = var.high_availability_enable
  # is_open_public_ip - (optional) is a type of bool
  is_open_public_ip = var.is_open_public_ip
  # key_pair_name - (optional) is a type of string
  key_pair_name = var.key_pair_name
  # master_pwd - (optional) is a type of string
  master_pwd = var.master_pwd
  # name - (required) is a type of string
  name = var.name
  # option_software_list - (optional) is a type of list of string
  option_software_list = var.option_software_list
  # period - (optional) is a type of number
  period = var.period
  # related_cluster_id - (optional) is a type of string
  related_cluster_id = var.related_cluster_id
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # ssh_enable - (optional) is a type of bool
  ssh_enable = var.ssh_enable
  # tags - (optional) is a type of map of string
  tags = var.tags
  # use_local_metadb - (optional) is a type of bool
  use_local_metadb = var.use_local_metadb
  # user_defined_emr_ecs_role - (optional) is a type of string
  user_defined_emr_ecs_role = var.user_defined_emr_ecs_role
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "bootstrap_action" {
    for_each = var.bootstrap_action
    content {
      # arg - (optional) is a type of string
      arg = bootstrap_action.value["arg"]
      # name - (optional) is a type of string
      name = bootstrap_action.value["name"]
      # path - (optional) is a type of string
      path = bootstrap_action.value["path"]
    }
  }

  dynamic "host_group" {
    for_each = var.host_group
    content {
      # auto_renew - (optional) is a type of bool
      auto_renew = host_group.value["auto_renew"]
      # charge_type - (optional) is a type of string
      charge_type = host_group.value["charge_type"]
      # disk_capacity - (optional) is a type of string
      disk_capacity = host_group.value["disk_capacity"]
      # disk_count - (optional) is a type of string
      disk_count = host_group.value["disk_count"]
      # disk_type - (optional) is a type of string
      disk_type = host_group.value["disk_type"]
      # gpu_driver - (optional) is a type of string
      gpu_driver = host_group.value["gpu_driver"]
      # host_group_name - (optional) is a type of string
      host_group_name = host_group.value["host_group_name"]
      # host_group_type - (optional) is a type of string
      host_group_type = host_group.value["host_group_type"]
      # instance_list - (optional) is a type of string
      instance_list = host_group.value["instance_list"]
      # instance_type - (optional) is a type of string
      instance_type = host_group.value["instance_type"]
      # node_count - (optional) is a type of string
      node_count = host_group.value["node_count"]
      # period - (optional) is a type of number
      period = host_group.value["period"]
      # sys_disk_capacity - (optional) is a type of string
      sys_disk_capacity = host_group.value["sys_disk_capacity"]
      # sys_disk_type - (optional) is a type of string
      sys_disk_type = host_group.value["sys_disk_type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_emr_cluster.this.id
}

output "this" {
  value = alicloud_emr_cluster.this
}
```

[top](#index)