# aws_dynamodb_global_table

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
module "aws_dynamodb_global_table" {
  source = "./modules/aws/r/aws_dynamodb_global_table"

  # name - (required) is a type of string
  name = null

  replica = [{
    region_name = null
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

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "replica" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      region_name = string
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

```terraform
resource "aws_dynamodb_global_table" "this" {
  name = var.name

  dynamic "replica" {
    for_each = var.replica
    content {
      region_name = replica.value["region_name"]
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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_dynamodb_global_table.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_dynamodb_global_table.this.id
}

output "this" {
  value = aws_dynamodb_global_table.this
}
```

[top](#index)