# aws_main_route_table_association

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
module "aws_main_route_table_association" {
  source = "./modules/aws/r/aws_main_route_table_association"

  # route_table_id - (required) is a type of string
  route_table_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```hcl
variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_main_route_table_association" "this" {
  route_table_id = var.route_table_id
  vpc_id         = var.vpc_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_main_route_table_association.this.id
}

output "original_route_table_id" {
  description = "returns a string"
  value       = aws_main_route_table_association.this.original_route_table_id
}

output "this" {
  value = aws_main_route_table_association.this
}
```

[top](#index)