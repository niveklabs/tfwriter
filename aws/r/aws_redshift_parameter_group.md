# aws_redshift_parameter_group

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_redshift_parameter_group" {
  source = "./modules/aws/r/aws_redshift_parameter_group"

  # description - (optional) is a type of string
  description = null
  # family - (required) is a type of string
  family = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  parameter = [{
    name  = null
    value = null
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

variable "family" {
  description = "(required)"
  type        = string
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

variable "parameter" {
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
resource "aws_redshift_parameter_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # family - (required) is a type of string
  family = var.family
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "parameter" {
    for_each = var.parameter
    content {
      # name - (required) is a type of string
      name = parameter.value["name"]
      # value - (required) is a type of string
      value = parameter.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_redshift_parameter_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_parameter_group.this.id
}

output "this" {
  value = aws_redshift_parameter_group.this
}
```

[top](#index)