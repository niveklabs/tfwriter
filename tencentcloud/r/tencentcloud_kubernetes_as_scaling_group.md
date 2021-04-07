# tencentcloud_kubernetes_as_scaling_group

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
module "tencentcloud_kubernetes_as_scaling_group" {
  source = "./modules/tencentcloud/r/tencentcloud_kubernetes_as_scaling_group"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # extra_args - (optional) is a type of list of string
  extra_args = []
  # labels - (optional) is a type of map of string
  labels = {}
  # unschedulable - (optional) is a type of number
  unschedulable = null

  auto_scaling_config = [{
    configuration_name = null
    data_disk = [{
      disk_size   = null
      disk_type   = null
      snapshot_id = null
    }]
    enhanced_monitor_service   = null
    enhanced_security_service  = null
    instance_tags              = {}
    instance_type              = null
    internet_charge_type       = null
    internet_max_bandwidth_out = null
    key_ids                    = []
    password                   = null
    project_id                 = null
    public_ip_assigned         = null
    security_group_ids         = []
    system_disk_size           = null
    system_disk_type           = null
  }]

  auto_scaling_group = [{
    default_cooldown = null
    desired_capacity = null
    forward_balancer_ids = [{
      listener_id      = null
      load_balancer_id = null
      rule_id          = null
      target_attribute = [{
        port   = null
        weight = null
      }]
    }]
    load_balancer_ids    = []
    max_size             = null
    min_size             = null
    project_id           = null
    retry_policy         = null
    scaling_group_name   = null
    subnet_ids           = []
    tags                 = {}
    termination_policies = []
    vpc_id               = null
    zones                = []
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

variable "extra_args" {
  description = "(optional) - Custom parameter information related to the node."
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of kubernetes AS Group created nodes."
  type        = map(string)
  default     = null
}

variable "unschedulable" {
  description = "(optional) - Sets whether the joining node participates in the schedule. Default is '0'. Participate in scheduling."
  type        = number
  default     = null
}

variable "auto_scaling_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      configuration_name = string
      data_disk = list(object(
        {
          disk_size   = number
          disk_type   = string
          snapshot_id = string
        }
      ))
      enhanced_monitor_service   = bool
      enhanced_security_service  = bool
      instance_tags              = map(string)
      instance_type              = string
      internet_charge_type       = string
      internet_max_bandwidth_out = number
      key_ids                    = list(string)
      password                   = string
      project_id                 = number
      public_ip_assigned         = bool
      security_group_ids         = list(string)
      system_disk_size           = number
      system_disk_type           = string
    }
  ))
}

variable "auto_scaling_group" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      default_cooldown = number
      desired_capacity = number
      forward_balancer_ids = list(object(
        {
          listener_id      = string
          load_balancer_id = string
          rule_id          = string
          target_attribute = list(object(
            {
              port   = number
              weight = number
            }
          ))
        }
      ))
      load_balancer_ids    = list(string)
      max_size             = number
      min_size             = number
      project_id           = number
      retry_policy         = string
      scaling_group_name   = string
      subnet_ids           = list(string)
      tags                 = map(string)
      termination_policies = list(string)
      vpc_id               = string
      zones                = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kubernetes_as_scaling_group" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # extra_args - (optional) is a type of list of string
  extra_args = var.extra_args
  # labels - (optional) is a type of map of string
  labels = var.labels
  # unschedulable - (optional) is a type of number
  unschedulable = var.unschedulable

  dynamic "auto_scaling_config" {
    for_each = var.auto_scaling_config
    content {
      # configuration_name - (required) is a type of string
      configuration_name = auto_scaling_config.value["configuration_name"]
      # enhanced_monitor_service - (optional) is a type of bool
      enhanced_monitor_service = auto_scaling_config.value["enhanced_monitor_service"]
      # enhanced_security_service - (optional) is a type of bool
      enhanced_security_service = auto_scaling_config.value["enhanced_security_service"]
      # instance_tags - (optional) is a type of map of string
      instance_tags = auto_scaling_config.value["instance_tags"]
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
      # project_id - (optional) is a type of number
      project_id = auto_scaling_config.value["project_id"]
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

  dynamic "auto_scaling_group" {
    for_each = var.auto_scaling_group
    content {
      # default_cooldown - (optional) is a type of number
      default_cooldown = auto_scaling_group.value["default_cooldown"]
      # desired_capacity - (optional) is a type of number
      desired_capacity = auto_scaling_group.value["desired_capacity"]
      # load_balancer_ids - (optional) is a type of list of string
      load_balancer_ids = auto_scaling_group.value["load_balancer_ids"]
      # max_size - (required) is a type of number
      max_size = auto_scaling_group.value["max_size"]
      # min_size - (required) is a type of number
      min_size = auto_scaling_group.value["min_size"]
      # project_id - (optional) is a type of number
      project_id = auto_scaling_group.value["project_id"]
      # retry_policy - (optional) is a type of string
      retry_policy = auto_scaling_group.value["retry_policy"]
      # scaling_group_name - (required) is a type of string
      scaling_group_name = auto_scaling_group.value["scaling_group_name"]
      # subnet_ids - (optional) is a type of list of string
      subnet_ids = auto_scaling_group.value["subnet_ids"]
      # tags - (optional) is a type of map of string
      tags = auto_scaling_group.value["tags"]
      # termination_policies - (optional) is a type of list of string
      termination_policies = auto_scaling_group.value["termination_policies"]
      # vpc_id - (required) is a type of string
      vpc_id = auto_scaling_group.value["vpc_id"]
      # zones - (optional) is a type of list of string
      zones = auto_scaling_group.value["zones"]

      dynamic "forward_balancer_ids" {
        for_each = auto_scaling_group.value.forward_balancer_ids
        content {
          # listener_id - (required) is a type of string
          listener_id = forward_balancer_ids.value["listener_id"]
          # load_balancer_id - (required) is a type of string
          load_balancer_id = forward_balancer_ids.value["load_balancer_id"]
          # rule_id - (optional) is a type of string
          rule_id = forward_balancer_ids.value["rule_id"]

          dynamic "target_attribute" {
            for_each = forward_balancer_ids.value.target_attribute
            content {
              # port - (required) is a type of number
              port = target_attribute.value["port"]
              # weight - (required) is a type of number
              weight = target_attribute.value["weight"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_as_scaling_group.this.id
}

output "this" {
  value = tencentcloud_kubernetes_as_scaling_group.this
}
```

[top](#index)