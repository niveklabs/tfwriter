# tencentcloud_as_scaling_group

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
module "tencentcloud_as_scaling_group" {
  source = "./modules/tencentcloud/r/tencentcloud_as_scaling_group"

  # configuration_id - (required) is a type of string
  configuration_id = null
  # default_cooldown - (optional) is a type of number
  default_cooldown = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # load_balancer_ids - (optional) is a type of list of string
  load_balancer_ids = []
  # max_size - (required) is a type of number
  max_size = null
  # min_size - (required) is a type of number
  min_size = null
  # project_id - (optional) is a type of number
  project_id = null
  # retry_policy - (optional) is a type of string
  retry_policy = null
  # scaling_group_name - (required) is a type of string
  scaling_group_name = null
  # subnet_ids - (optional) is a type of list of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
  # termination_policies - (optional) is a type of list of string
  termination_policies = []
  # vpc_id - (required) is a type of string
  vpc_id = null
  # zones - (optional) is a type of list of string
  zones = []

  forward_balancer_ids = [{
    listener_id      = null
    load_balancer_id = null
    rule_id          = null
    target_attribute = [{
      port   = null
      weight = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "configuration_id" {
  description = "(required) - An available ID for a launch configuration."
  type        = string
}

variable "default_cooldown" {
  description = "(optional) - Default cooldown time in second, and default value is `300`."
  type        = number
  default     = null
}

variable "desired_capacity" {
  description = "(optional) - Desired volume of CVM instances, which is between `max_size` and `min_size`."
  type        = number
  default     = null
}

variable "load_balancer_ids" {
  description = "(optional) - ID list of traditional load balancers."
  type        = list(string)
  default     = null
}

variable "max_size" {
  description = "(required) - Maximum number of CVM instances. Valid value ranges: (0~2000)."
  type        = number
}

variable "min_size" {
  description = "(required) - Minimum number of CVM instances. Valid value ranges: (0~2000)."
  type        = number
}

variable "project_id" {
  description = "(optional) - Specifies to which project the scaling group belongs."
  type        = number
  default     = null
}

variable "retry_policy" {
  description = "(optional) - Available values for retry policies. Valid values: IMMEDIATE_RETRY and INCREMENTAL_INTERVALS."
  type        = string
  default     = null
}

variable "scaling_group_name" {
  description = "(required) - Name of a scaling group."
  type        = string
}

variable "subnet_ids" {
  description = "(optional) - ID list of subnet, and for VPC it is required."
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of a scaling group."
  type        = map(string)
  default     = null
}

variable "termination_policies" {
  description = "(optional) - Available values for termination policies. Valid values: OLDEST_INSTANCE and NEWEST_INSTANCE."
  type        = list(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of VPC network."
  type        = string
}

variable "zones" {
  description = "(optional) - List of available zones, for Basic network it is required."
  type        = list(string)
  default     = null
}

variable "forward_balancer_ids" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_scaling_group" "this" {
  configuration_id     = var.configuration_id
  default_cooldown     = var.default_cooldown
  desired_capacity     = var.desired_capacity
  load_balancer_ids    = var.load_balancer_ids
  max_size             = var.max_size
  min_size             = var.min_size
  project_id           = var.project_id
  retry_policy         = var.retry_policy
  scaling_group_name   = var.scaling_group_name
  subnet_ids           = var.subnet_ids
  tags                 = var.tags
  termination_policies = var.termination_policies
  vpc_id               = var.vpc_id
  zones                = var.zones

  dynamic "forward_balancer_ids" {
    for_each = var.forward_balancer_ids
    content {
      listener_id      = forward_balancer_ids.value["listener_id"]
      load_balancer_id = forward_balancer_ids.value["load_balancer_id"]
      rule_id          = forward_balancer_ids.value["rule_id"]

      dynamic "target_attribute" {
        for_each = forward_balancer_ids.value.target_attribute
        content {
          port   = target_attribute.value["port"]
          weight = target_attribute.value["weight"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_group.this.create_time
}

output "desired_capacity" {
  description = "returns a number"
  value       = tencentcloud_as_scaling_group.this.desired_capacity
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_group.this.id
}

output "instance_count" {
  description = "returns a number"
  value       = tencentcloud_as_scaling_group.this.instance_count
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_group.this.status
}

output "termination_policies" {
  description = "returns a list of string"
  value       = tencentcloud_as_scaling_group.this.termination_policies
}

output "this" {
  value = tencentcloud_as_scaling_group.this
}
```

[top](#index)