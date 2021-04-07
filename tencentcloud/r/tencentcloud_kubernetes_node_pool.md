# tencentcloud_kubernetes_node_pool

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_kubernetes_node_pool" {
  source = "./modules/tencentcloud/r/tencentcloud_kubernetes_node_pool"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # delete_keep_instance - (optional) is a type of bool
  delete_keep_instance = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # enable_auto_scale - (optional) is a type of bool
  enable_auto_scale = null
  # labels - (optional) is a type of map of string
  labels = {}
  # max_size - (required) is a type of number
  max_size = null
  # min_size - (required) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # node_os - (optional) is a type of string
  node_os = null
  # node_os_type - (optional) is a type of string
  node_os_type = null
  # retry_policy - (optional) is a type of string
  retry_policy = null
  # scaling_mode - (optional) is a type of string
  scaling_mode = null
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = []
  # unschedulable - (optional) is a type of number
  unschedulable = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  auto_scaling_config = [{
    data_disk = [{
      disk_size   = null
      disk_type   = null
      snapshot_id = null
    }]
    enhanced_monitor_service   = null
    enhanced_security_service  = null
    instance_type              = null
    internet_charge_type       = null
    internet_max_bandwidth_out = null
    key_ids                    = []
    password                   = null
    public_ip_assigned         = null
    security_group_ids         = []
    system_disk_size           = null
    system_disk_type           = null
  }]

  node_config = [{
    data_disk = [{
      auto_format_and_mount = null
      disk_size             = null
      disk_type             = null
      file_system           = null
      mount_target          = null
    }]
    docker_graph_path = null
    extra_args        = []
    is_schedule       = null
    mount_target      = null
    user_data         = null
  }]

  taints = [{
    effect = null
    key    = null
    value  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the cluster."
  type        = string
}

variable "delete_keep_instance" {
  description = "(optional) - Indicate to keep the CVM instance when delete the node pool. Default is `true`."
  type        = bool
  default     = null
}

variable "desired_capacity" {
  description = "(optional) - Desired capacity ot the node. If `enable_auto_scale` is set `true`, this will be a computed parameter."
  type        = number
  default     = null
}

variable "enable_auto_scale" {
  description = "(optional) - Indicate whether to enable auto scaling or not."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of kubernetes node pool created nodes. The label key name does not exceed 63 characters, only supports English, numbers,'/','-', and does not allow beginning with ('/')."
  type        = map(string)
  default     = null
}

variable "max_size" {
  description = "(required) - Maximum number of node."
  type        = number
}

variable "min_size" {
  description = "(required) - Minimum number of node."
  type        = number
}

variable "name" {
  description = "(required) - Name of the node pool. The name does not exceed 25 characters, and only supports Chinese, English, numbers, underscores, separators (`-`) and decimal points."
  type        = string
}

variable "node_os" {
  description = "(optional) - Operating system of the cluster, the available values include: `tlinux2.4x86_64`, `ubuntu18.04.1x86_64`, `ubuntu16.04.1 LTSx86_64`, `centos7.6.0_x64` and `centos7.2x86_64`. Default is 'tlinux2.4x86_64'. This parameter will only affect new nodes, not including the existing nodes."
  type        = string
  default     = null
}

variable "node_os_type" {
  description = "(optional) - The image version of the node. Valida values are `DOCKER_CUSTOMIZE` and `GENERAL`. Default is `GENERAL`. This parameter will only affect new nodes, not including the existing nodes."
  type        = string
  default     = null
}

variable "retry_policy" {
  description = "(optional) - Available values for retry policies include `IMMEDIATE_RETRY` and `INCREMENTAL_INTERVALS`."
  type        = string
  default     = null
}

variable "scaling_mode" {
  description = "(optional) - Auto scaling mode. Valid values are `CLASSIC_SCALING`(scaling by create/destroy instances), `WAKE_UP_STOPPED_SCALING`(Boot priority for expansion. When expanding the capacity, the shutdown operation is given priority to the shutdown of the instance. If the number of instances is still lower than the expected number of instances after the startup, the instance will be created, and the method of destroying the instance will still be used for shrinking)."
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(optional) - ID list of subnet, and for VPC it is required."
  type        = list(string)
  default     = null
}

variable "unschedulable" {
  description = "(optional) - Sets whether the joining node participates in the schedule. Default is '0'. Participate in scheduling."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of VPC network."
  type        = string
}

variable "auto_scaling_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      data_disk = list(object(
        {
          disk_size   = number
          disk_type   = string
          snapshot_id = string
        }
      ))
      enhanced_monitor_service   = bool
      enhanced_security_service  = bool
      instance_type              = string
      internet_charge_type       = string
      internet_max_bandwidth_out = number
      key_ids                    = list(string)
      password                   = string
      public_ip_assigned         = bool
      security_group_ids         = list(string)
      system_disk_size           = number
      system_disk_type           = string
    }
  ))
}

variable "node_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_disk = list(object(
        {
          auto_format_and_mount = bool
          disk_size             = number
          disk_type             = string
          file_system           = string
          mount_target          = string
        }
      ))
      docker_graph_path = string
      extra_args        = list(string)
      is_schedule       = bool
      mount_target      = string
      user_data         = string
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
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kubernetes_node_pool" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # delete_keep_instance - (optional) is a type of bool
  delete_keep_instance = var.delete_keep_instance
  # desired_capacity - (optional) is a type of number
  desired_capacity = var.desired_capacity
  # enable_auto_scale - (optional) is a type of bool
  enable_auto_scale = var.enable_auto_scale
  # labels - (optional) is a type of map of string
  labels = var.labels
  # max_size - (required) is a type of number
  max_size = var.max_size
  # min_size - (required) is a type of number
  min_size = var.min_size
  # name - (required) is a type of string
  name = var.name
  # node_os - (optional) is a type of string
  node_os = var.node_os
  # node_os_type - (optional) is a type of string
  node_os_type = var.node_os_type
  # retry_policy - (optional) is a type of string
  retry_policy = var.retry_policy
  # scaling_mode - (optional) is a type of string
  scaling_mode = var.scaling_mode
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = var.subnet_ids
  # unschedulable - (optional) is a type of number
  unschedulable = var.unschedulable
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id

  dynamic "auto_scaling_config" {
    for_each = var.auto_scaling_config
    content {
      # enhanced_monitor_service - (optional) is a type of bool
      enhanced_monitor_service = auto_scaling_config.value["enhanced_monitor_service"]
      # enhanced_security_service - (optional) is a type of bool
      enhanced_security_service = auto_scaling_config.value["enhanced_security_service"]
      # instance_type - (required) is a type of string
      instance_type = auto_scaling_config.value["instance_type"]
      # internet_charge_type - (optional) is a type of string
      internet_charge_type = auto_scaling_config.value["internet_charge_type"]
      # internet_max_bandwidth_out - (optional) is a type of number
      internet_max_bandwidth_out = auto_scaling_config.value["internet_max_bandwidth_out"]
      # key_ids - (optional) is a type of list of string
      key_ids = auto_scaling_config.value["key_ids"]
      # password - (optional) is a type of string
      password = auto_scaling_config.value["password"]
      # public_ip_assigned - (optional) is a type of bool
      public_ip_assigned = auto_scaling_config.value["public_ip_assigned"]
      # security_group_ids - (optional) is a type of list of string
      security_group_ids = auto_scaling_config.value["security_group_ids"]
      # system_disk_size - (optional) is a type of number
      system_disk_size = auto_scaling_config.value["system_disk_size"]
      # system_disk_type - (optional) is a type of string
      system_disk_type = auto_scaling_config.value["system_disk_type"]

      dynamic "data_disk" {
        for_each = auto_scaling_config.value.data_disk
        content {
          # disk_size - (optional) is a type of number
          disk_size = data_disk.value["disk_size"]
          # disk_type - (optional) is a type of string
          disk_type = data_disk.value["disk_type"]
          # snapshot_id - (optional) is a type of string
          snapshot_id = data_disk.value["snapshot_id"]
        }
      }

    }
  }

  dynamic "node_config" {
    for_each = var.node_config
    content {
      # docker_graph_path - (optional) is a type of string
      docker_graph_path = node_config.value["docker_graph_path"]
      # extra_args - (optional) is a type of list of string
      extra_args = node_config.value["extra_args"]
      # is_schedule - (optional) is a type of bool
      is_schedule = node_config.value["is_schedule"]
      # mount_target - (optional) is a type of string
      mount_target = node_config.value["mount_target"]
      # user_data - (optional) is a type of string
      user_data = node_config.value["user_data"]

      dynamic "data_disk" {
        for_each = node_config.value.data_disk
        content {
          # auto_format_and_mount - (optional) is a type of bool
          auto_format_and_mount = data_disk.value["auto_format_and_mount"]
          # disk_size - (optional) is a type of number
          disk_size = data_disk.value["disk_size"]
          # disk_type - (optional) is a type of string
          disk_type = data_disk.value["disk_type"]
          # file_system - (optional) is a type of string
          file_system = data_disk.value["file_system"]
          # mount_target - (optional) is a type of string
          mount_target = data_disk.value["mount_target"]
        }
      }

    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      # effect - (required) is a type of string
      effect = taints.value["effect"]
      # key - (required) is a type of string
      key = taints.value["key"]
      # value - (required) is a type of string
      value = taints.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_scaling_group_id" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_node_pool.this.auto_scaling_group_id
}

output "desired_capacity" {
  description = "returns a number"
  value       = tencentcloud_kubernetes_node_pool.this.desired_capacity
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_node_pool.this.id
}

output "launch_config_id" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_node_pool.this.launch_config_id
}

output "node_count" {
  description = "returns a number"
  value       = tencentcloud_kubernetes_node_pool.this.node_count
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_node_pool.this.status
}

output "this" {
  value = tencentcloud_kubernetes_node_pool.this
}
```

[top](#index)