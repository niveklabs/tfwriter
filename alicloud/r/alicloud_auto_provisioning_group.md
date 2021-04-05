# alicloud_auto_provisioning_group

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
module "alicloud_auto_provisioning_group" {
  source = "./modules/alicloud/r/alicloud_auto_provisioning_group"

  # auto_provisioning_group_name - (optional) is a type of string
  auto_provisioning_group_name = null
  # auto_provisioning_group_type - (optional) is a type of string
  auto_provisioning_group_type = null
  # default_target_capacity_type - (optional) is a type of string
  default_target_capacity_type = null
  # description - (optional) is a type of string
  description = null
  # excess_capacity_termination_policy - (optional) is a type of string
  excess_capacity_termination_policy = null
  # launch_template_id - (required) is a type of string
  launch_template_id = null
  # launch_template_version - (optional) is a type of string
  launch_template_version = null
  # max_spot_price - (optional) is a type of number
  max_spot_price = null
  # pay_as_you_go_allocation_strategy - (optional) is a type of string
  pay_as_you_go_allocation_strategy = null
  # pay_as_you_go_target_capacity - (optional) is a type of string
  pay_as_you_go_target_capacity = null
  # spot_allocation_strategy - (optional) is a type of string
  spot_allocation_strategy = null
  # spot_instance_interruption_behavior - (optional) is a type of string
  spot_instance_interruption_behavior = null
  # spot_instance_pools_to_use_count - (optional) is a type of number
  spot_instance_pools_to_use_count = null
  # spot_target_capacity - (optional) is a type of string
  spot_target_capacity = null
  # terminate_instances - (optional) is a type of bool
  terminate_instances = null
  # terminate_instances_with_expiration - (optional) is a type of bool
  terminate_instances_with_expiration = null
  # total_target_capacity - (required) is a type of string
  total_target_capacity = null
  # valid_from - (optional) is a type of string
  valid_from = null
  # valid_until - (optional) is a type of string
  valid_until = null

  launch_template_config = [{
    instance_type     = null
    max_price         = null
    priority          = null
    vswitch_id        = null
    weighted_capacity = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_provisioning_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_provisioning_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_target_capacity_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "excess_capacity_termination_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_template_id" {
  description = "(required)"
  type        = string
}

variable "launch_template_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_spot_price" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pay_as_you_go_allocation_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pay_as_you_go_target_capacity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_allocation_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_instance_interruption_behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_instance_pools_to_use_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spot_target_capacity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "terminate_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "terminate_instances_with_expiration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "total_target_capacity" {
  description = "(required)"
  type        = string
}

variable "valid_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "valid_until" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_template_config" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      instance_type     = string
      max_price         = string
      priority          = string
      vswitch_id        = string
      weighted_capacity = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_auto_provisioning_group" "this" {
  auto_provisioning_group_name        = var.auto_provisioning_group_name
  auto_provisioning_group_type        = var.auto_provisioning_group_type
  default_target_capacity_type        = var.default_target_capacity_type
  description                         = var.description
  excess_capacity_termination_policy  = var.excess_capacity_termination_policy
  launch_template_id                  = var.launch_template_id
  launch_template_version             = var.launch_template_version
  max_spot_price                      = var.max_spot_price
  pay_as_you_go_allocation_strategy   = var.pay_as_you_go_allocation_strategy
  pay_as_you_go_target_capacity       = var.pay_as_you_go_target_capacity
  spot_allocation_strategy            = var.spot_allocation_strategy
  spot_instance_interruption_behavior = var.spot_instance_interruption_behavior
  spot_instance_pools_to_use_count    = var.spot_instance_pools_to_use_count
  spot_target_capacity                = var.spot_target_capacity
  terminate_instances                 = var.terminate_instances
  terminate_instances_with_expiration = var.terminate_instances_with_expiration
  total_target_capacity               = var.total_target_capacity
  valid_from                          = var.valid_from
  valid_until                         = var.valid_until

  dynamic "launch_template_config" {
    for_each = var.launch_template_config
    content {
      instance_type     = launch_template_config.value["instance_type"]
      max_price         = launch_template_config.value["max_price"]
      priority          = launch_template_config.value["priority"]
      vswitch_id        = launch_template_config.value["vswitch_id"]
      weighted_capacity = launch_template_config.value["weighted_capacity"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_provisioning_group_name" {
  description = "returns a string"
  value       = alicloud_auto_provisioning_group.this.auto_provisioning_group_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_auto_provisioning_group.this.id
}

output "launch_template_version" {
  description = "returns a string"
  value       = alicloud_auto_provisioning_group.this.launch_template_version
}

output "max_spot_price" {
  description = "returns a number"
  value       = alicloud_auto_provisioning_group.this.max_spot_price
}

output "spot_instance_pools_to_use_count" {
  description = "returns a number"
  value       = alicloud_auto_provisioning_group.this.spot_instance_pools_to_use_count
}

output "valid_from" {
  description = "returns a string"
  value       = alicloud_auto_provisioning_group.this.valid_from
}

output "valid_until" {
  description = "returns a string"
  value       = alicloud_auto_provisioning_group.this.valid_until
}

output "this" {
  value = alicloud_auto_provisioning_group.this
}
```

[top](#index)