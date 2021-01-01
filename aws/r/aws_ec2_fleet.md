# aws_ec2_fleet

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_ec2_fleet" {
  source = "./modules/aws/r/aws_ec2_fleet"

  # excess_capacity_termination_policy - (optional) is a type of string
  excess_capacity_termination_policy = null
  # replace_unhealthy_instances - (optional) is a type of bool
  replace_unhealthy_instances = null
  # tags - (optional) is a type of map of string
  tags = {}
  # terminate_instances - (optional) is a type of bool
  terminate_instances = null
  # terminate_instances_with_expiration - (optional) is a type of bool
  terminate_instances_with_expiration = null
  # type - (optional) is a type of string
  type = null

  launch_template_config = [{
    launch_template_specification = [{
      launch_template_id   = null
      launch_template_name = null
      version              = null
    }]
    override = [{
      availability_zone = null
      instance_type     = null
      max_price         = null
      priority          = null
      subnet_id         = null
      weighted_capacity = null
    }]
  }]

  on_demand_options = [{
    allocation_strategy = null
  }]

  spot_options = [{
    allocation_strategy            = null
    instance_interruption_behavior = null
    instance_pools_to_use_count    = null
    maintenance_strategies = [{
      capacity_rebalance = [{
        replacement_strategy = null
      }]
    }]
  }]

  target_capacity_specification = [{
    default_target_capacity_type = null
    on_demand_target_capacity    = null
    spot_target_capacity         = null
    total_target_capacity        = null
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

```hcl
variable "excess_capacity_termination_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replace_unhealthy_instances" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "launch_template_config" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      launch_template_specification = list(object(
        {
          launch_template_id   = string
          launch_template_name = string
          version              = string
        }
      ))
      override = list(object(
        {
          availability_zone = string
          instance_type     = string
          max_price         = string
          priority          = number
          subnet_id         = string
          weighted_capacity = number
        }
      ))
    }
  ))
}

variable "on_demand_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allocation_strategy = string
    }
  ))
  default = []
}

variable "spot_options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allocation_strategy            = string
      instance_interruption_behavior = string
      instance_pools_to_use_count    = number
      maintenance_strategies = list(object(
        {
          capacity_rebalance = list(object(
            {
              replacement_strategy = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "target_capacity_specification" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      default_target_capacity_type = string
      on_demand_target_capacity    = number
      spot_target_capacity         = number
      total_target_capacity        = number
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "aws_ec2_fleet" "this" {
  excess_capacity_termination_policy  = var.excess_capacity_termination_policy
  replace_unhealthy_instances         = var.replace_unhealthy_instances
  tags                                = var.tags
  terminate_instances                 = var.terminate_instances
  terminate_instances_with_expiration = var.terminate_instances_with_expiration
  type                                = var.type

  dynamic "launch_template_config" {
    for_each = var.launch_template_config
    content {

      dynamic "launch_template_specification" {
        for_each = launch_template_config.value.launch_template_specification
        content {
          launch_template_id   = launch_template_specification.value["launch_template_id"]
          launch_template_name = launch_template_specification.value["launch_template_name"]
          version              = launch_template_specification.value["version"]
        }
      }

      dynamic "override" {
        for_each = launch_template_config.value.override
        content {
          availability_zone = override.value["availability_zone"]
          instance_type     = override.value["instance_type"]
          max_price         = override.value["max_price"]
          priority          = override.value["priority"]
          subnet_id         = override.value["subnet_id"]
          weighted_capacity = override.value["weighted_capacity"]
        }
      }

    }
  }

  dynamic "on_demand_options" {
    for_each = var.on_demand_options
    content {
      allocation_strategy = on_demand_options.value["allocation_strategy"]
    }
  }

  dynamic "spot_options" {
    for_each = var.spot_options
    content {
      allocation_strategy            = spot_options.value["allocation_strategy"]
      instance_interruption_behavior = spot_options.value["instance_interruption_behavior"]
      instance_pools_to_use_count    = spot_options.value["instance_pools_to_use_count"]

      dynamic "maintenance_strategies" {
        for_each = spot_options.value.maintenance_strategies
        content {

          dynamic "capacity_rebalance" {
            for_each = maintenance_strategies.value.capacity_rebalance
            content {
              replacement_strategy = capacity_rebalance.value["replacement_strategy"]
            }
          }

        }
      }

    }
  }

  dynamic "target_capacity_specification" {
    for_each = var.target_capacity_specification
    content {
      default_target_capacity_type = target_capacity_specification.value["default_target_capacity_type"]
      on_demand_target_capacity    = target_capacity_specification.value["on_demand_target_capacity"]
      spot_target_capacity         = target_capacity_specification.value["spot_target_capacity"]
      total_target_capacity        = target_capacity_specification.value["total_target_capacity"]
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

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_fleet.this.id
}

output "this" {
  value = aws_ec2_fleet.this
}
```

[top](#index)