# aws_emr_instance_fleet

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_emr_instance_fleet" {
  source = "./modules/aws/r/aws_emr_instance_fleet"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (optional) is a type of string
  name = null
  # target_on_demand_capacity - (optional) is a type of number
  target_on_demand_capacity = null
  # target_spot_capacity - (optional) is a type of number
  target_spot_capacity = null

  instance_type_configs = [{
    bid_price                                  = null
    bid_price_as_percentage_of_on_demand_price = null
    configurations = [{
      classification = null
      properties     = {}
    }]
    ebs_config = [{
      iops                 = null
      size                 = null
      type                 = null
      volumes_per_instance = null
    }]
    instance_type     = null
    weighted_capacity = null
  }]

  launch_specifications = [{
    on_demand_specification = [{
      allocation_strategy = null
    }]
    spot_specification = [{
      allocation_strategy      = null
      block_duration_minutes   = null
      timeout_action           = null
      timeout_duration_minutes = null
    }]
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_on_demand_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target_spot_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type_configs" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bid_price                                  = string
      bid_price_as_percentage_of_on_demand_price = number
      configurations = set(object(
        {
          classification = string
          properties     = map(string)
        }
      ))
      ebs_config = set(object(
        {
          iops                 = number
          size                 = number
          type                 = string
          volumes_per_instance = number
        }
      ))
      instance_type     = string
      weighted_capacity = number
    }
  ))
  default = []
}

variable "launch_specifications" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      on_demand_specification = list(object(
        {
          allocation_strategy = string
        }
      ))
      spot_specification = list(object(
        {
          allocation_strategy      = string
          block_duration_minutes   = number
          timeout_action           = string
          timeout_duration_minutes = number
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
resource "aws_emr_instance_fleet" "this" {
  cluster_id                = var.cluster_id
  name                      = var.name
  target_on_demand_capacity = var.target_on_demand_capacity
  target_spot_capacity      = var.target_spot_capacity

  dynamic "instance_type_configs" {
    for_each = var.instance_type_configs
    content {
      bid_price                                  = instance_type_configs.value["bid_price"]
      bid_price_as_percentage_of_on_demand_price = instance_type_configs.value["bid_price_as_percentage_of_on_demand_price"]
      instance_type                              = instance_type_configs.value["instance_type"]
      weighted_capacity                          = instance_type_configs.value["weighted_capacity"]

      dynamic "configurations" {
        for_each = instance_type_configs.value.configurations
        content {
          classification = configurations.value["classification"]
          properties     = configurations.value["properties"]
        }
      }

      dynamic "ebs_config" {
        for_each = instance_type_configs.value.ebs_config
        content {
          iops                 = ebs_config.value["iops"]
          size                 = ebs_config.value["size"]
          type                 = ebs_config.value["type"]
          volumes_per_instance = ebs_config.value["volumes_per_instance"]
        }
      }

    }
  }

  dynamic "launch_specifications" {
    for_each = var.launch_specifications
    content {

      dynamic "on_demand_specification" {
        for_each = launch_specifications.value.on_demand_specification
        content {
          allocation_strategy = on_demand_specification.value["allocation_strategy"]
        }
      }

      dynamic "spot_specification" {
        for_each = launch_specifications.value.spot_specification
        content {
          allocation_strategy      = spot_specification.value["allocation_strategy"]
          block_duration_minutes   = spot_specification.value["block_duration_minutes"]
          timeout_action           = spot_specification.value["timeout_action"]
          timeout_duration_minutes = spot_specification.value["timeout_duration_minutes"]
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
  value       = aws_emr_instance_fleet.this.id
}

output "provisioned_on_demand_capacity" {
  description = "returns a number"
  value       = aws_emr_instance_fleet.this.provisioned_on_demand_capacity
}

output "provisioned_spot_capacity" {
  description = "returns a number"
  value       = aws_emr_instance_fleet.this.provisioned_spot_capacity
}

output "this" {
  value = aws_emr_instance_fleet.this
}
```

[top](#index)