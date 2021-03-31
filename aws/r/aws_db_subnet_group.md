# aws_db_subnet_group

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
module "aws_db_subnet_group" {
  source = "./modules/aws/r/aws_db_subnet_group"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_db_subnet_group" "this" {
  description = var.description
  name        = var.name
  name_prefix = var.name_prefix
  subnet_ids  = var.subnet_ids
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_db_subnet_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_db_subnet_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_db_subnet_group.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_db_subnet_group.this.name_prefix
}

output "this" {
  value = aws_db_subnet_group.this
}
```

[top](#index)