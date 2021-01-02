# aws_ecs_cluster

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
module "aws_ecs_cluster" {
  source = "./modules/aws/r/aws_ecs_cluster"

  # capacity_providers - (optional) is a type of set of string
  capacity_providers = []
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  default_capacity_provider_strategy = [{
    base              = null
    capacity_provider = null
    weight            = null
  }]

  setting = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "capacity_providers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "default_capacity_provider_strategy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      base              = number
      capacity_provider = string
      weight            = number
    }
  ))
  default = []
}

variable "setting" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ecs_cluster" "this" {
  capacity_providers = var.capacity_providers
  name               = var.name
  tags               = var.tags

  dynamic "default_capacity_provider_strategy" {
    for_each = var.default_capacity_provider_strategy
    content {
      base              = default_capacity_provider_strategy.value["base"]
      capacity_provider = default_capacity_provider_strategy.value["capacity_provider"]
      weight            = default_capacity_provider_strategy.value["weight"]
    }
  }

  dynamic "setting" {
    for_each = var.setting
    content {
      name  = setting.value["name"]
      value = setting.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ecs_cluster.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ecs_cluster.this.id
}

output "this" {
  value = aws_ecs_cluster.this
}
```

[top](#index)