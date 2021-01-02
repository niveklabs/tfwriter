# aws_docdb_cluster_parameter_group

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
module "aws_docdb_cluster_parameter_group" {
  source = "./modules/aws/r/aws_docdb_cluster_parameter_group"

  # description - (optional) is a type of string
  description = null
  # family - (required) is a type of string
  family = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # tags - (optional) is a type of map of string
  tags = {}

  parameter = [{
    apply_method = null
    name         = null
    value        = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
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
      apply_method = string
      name         = string
      value        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_docdb_cluster_parameter_group" "this" {
  description = var.description
  family      = var.family
  name        = var.name
  name_prefix = var.name_prefix
  tags        = var.tags

  dynamic "parameter" {
    for_each = var.parameter
    content {
      apply_method = parameter.value["apply_method"]
      name         = parameter.value["name"]
      value        = parameter.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_docdb_cluster_parameter_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_docdb_cluster_parameter_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_docdb_cluster_parameter_group.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_docdb_cluster_parameter_group.this.name_prefix
}

output "this" {
  value = aws_docdb_cluster_parameter_group.this
}
```

[top](#index)