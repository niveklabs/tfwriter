# aws_dax_subnet_group

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
module "aws_dax_subnet_group" {
  source = "./modules/aws/r/aws_dax_subnet_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
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

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "aws_dax_subnet_group" "this" {
  description = var.description
  name        = var.name
  subnet_ids  = var.subnet_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_dax_subnet_group.this.id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_dax_subnet_group.this.vpc_id
}

output "this" {
  value = aws_dax_subnet_group.this
}
```

[top](#index)