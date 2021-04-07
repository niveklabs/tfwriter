# alicloud_ess_scaling_group

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
module "alicloud_ess_scaling_group" {
  source = "./modules/alicloud/r/alicloud_ess_scaling_group"

  # db_instance_ids - (optional) is a type of set of string
  db_instance_ids = []
  # default_cooldown - (optional) is a type of number
  default_cooldown = null
  # desired_capacity - (optional) is a type of number
  desired_capacity = null
  # group_deletion_protection - (optional) is a type of bool
  group_deletion_protection = null
  # loadbalancer_ids - (optional) is a type of set of string
  loadbalancer_ids = []
  # max_size - (required) is a type of number
  max_size = null
  # min_size - (required) is a type of number
  min_size = null
  # multi_az_policy - (optional) is a type of string
  multi_az_policy = null
  # on_demand_base_capacity - (optional) is a type of number
  on_demand_base_capacity = null
  # on_demand_percentage_above_base_capacity - (optional) is a type of number
  on_demand_percentage_above_base_capacity = null
  # removal_policies - (optional) is a type of list of string
  removal_policies = []
  # scaling_group_name - (optional) is a type of string
  scaling_group_name = null
  # spot_instance_pools - (optional) is a type of number
  spot_instance_pools = null
  # spot_instance_remedy - (optional) is a type of bool
  spot_instance_remedy = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # vswitch_ids - (optional) is a type of set of string
  vswitch_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "db_instance_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "default_cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "desired_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "group_deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "loadbalancer_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "max_size" {
  description = "(required)"
  type        = number
}

variable "min_size" {
  description = "(required)"
  type        = number
}

variable "multi_az_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_demand_base_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "on_demand_percentage_above_base_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "removal_policies" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "scaling_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_instance_pools" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spot_instance_remedy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_scaling_group" "this" {
  # db_instance_ids - (optional) is a type of set of string
  db_instance_ids = var.db_instance_ids
  # default_cooldown - (optional) is a type of number
  default_cooldown = var.default_cooldown
  # desired_capacity - (optional) is a type of number
  desired_capacity = var.desired_capacity
  # group_deletion_protection - (optional) is a type of bool
  group_deletion_protection = var.group_deletion_protection
  # loadbalancer_ids - (optional) is a type of set of string
  loadbalancer_ids = var.loadbalancer_ids
  # max_size - (required) is a type of number
  max_size = var.max_size
  # min_size - (required) is a type of number
  min_size = var.min_size
  # multi_az_policy - (optional) is a type of string
  multi_az_policy = var.multi_az_policy
  # on_demand_base_capacity - (optional) is a type of number
  on_demand_base_capacity = var.on_demand_base_capacity
  # on_demand_percentage_above_base_capacity - (optional) is a type of number
  on_demand_percentage_above_base_capacity = var.on_demand_percentage_above_base_capacity
  # removal_policies - (optional) is a type of list of string
  removal_policies = var.removal_policies
  # scaling_group_name - (optional) is a type of string
  scaling_group_name = var.scaling_group_name
  # spot_instance_pools - (optional) is a type of number
  spot_instance_pools = var.spot_instance_pools
  # spot_instance_remedy - (optional) is a type of bool
  spot_instance_remedy = var.spot_instance_remedy
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # vswitch_ids - (optional) is a type of set of string
  vswitch_ids = var.vswitch_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ess_scaling_group.this.id
}

output "on_demand_base_capacity" {
  description = "returns a number"
  value       = alicloud_ess_scaling_group.this.on_demand_base_capacity
}

output "on_demand_percentage_above_base_capacity" {
  description = "returns a number"
  value       = alicloud_ess_scaling_group.this.on_demand_percentage_above_base_capacity
}

output "removal_policies" {
  description = "returns a list of string"
  value       = alicloud_ess_scaling_group.this.removal_policies
}

output "spot_instance_pools" {
  description = "returns a number"
  value       = alicloud_ess_scaling_group.this.spot_instance_pools
}

output "spot_instance_remedy" {
  description = "returns a bool"
  value       = alicloud_ess_scaling_group.this.spot_instance_remedy
}

output "this" {
  value = alicloud_ess_scaling_group.this
}
```

[top](#index)