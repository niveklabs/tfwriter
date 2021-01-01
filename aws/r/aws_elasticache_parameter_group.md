# aws_elasticache_parameter_group

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
module "aws_elasticache_parameter_group" {
  source = "./modules/aws/r/aws_elasticache_parameter_group"

  # description - (optional) is a type of string
  description = null
  # family - (required) is a type of string
  family = null
  # name - (required) is a type of string
  name = null

  parameter = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "family" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
resource "aws_elasticache_parameter_group" "this" {
  description = var.description
  family      = var.family
  name        = var.name

  dynamic "parameter" {
    for_each = var.parameter
    content {
      name  = parameter.value["name"]
      value = parameter.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_elasticache_parameter_group.this.id
}

output "this" {
  value = aws_elasticache_parameter_group.this
}
```

[top](#index)