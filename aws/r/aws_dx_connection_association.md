# aws_dx_connection_association

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
module "aws_dx_connection_association" {
  source = "./modules/aws/r/aws_dx_connection_association"

  # connection_id - (required) is a type of string
  connection_id = null
  # lag_id - (required) is a type of string
  lag_id = null
}
```

[top](#index)

### Variables

```hcl
variable "connection_id" {
  description = "(required)"
  type        = string
}

variable "lag_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_dx_connection_association" "this" {
  connection_id = var.connection_id
  lag_id        = var.lag_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_dx_connection_association.this.id
}

output "this" {
  value = aws_dx_connection_association.this
}
```

[top](#index)