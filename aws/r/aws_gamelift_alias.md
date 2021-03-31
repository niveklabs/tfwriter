# aws_gamelift_alias

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_gamelift_alias" {
  source = "./modules/aws/r/aws_gamelift_alias"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  routing_strategy = [{
    fleet_id = null
    message  = null
    type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
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

variable "routing_strategy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      fleet_id = string
      message  = string
      type     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_gamelift_alias" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "routing_strategy" {
    for_each = var.routing_strategy
    content {
      fleet_id = routing_strategy.value["fleet_id"]
      message  = routing_strategy.value["message"]
      type     = routing_strategy.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_gamelift_alias.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_gamelift_alias.this.id
}

output "this" {
  value = aws_gamelift_alias.this
}
```

[top](#index)