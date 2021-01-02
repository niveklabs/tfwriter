# aws_qldb_ledger

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_qldb_ledger" {
  source = "./modules/aws/d/aws_qldb_ledger"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_qldb_ledger" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_qldb_ledger.this.arn
}

output "deletion_protection" {
  description = "returns a bool"
  value       = data.aws_qldb_ledger.this.deletion_protection
}

output "id" {
  description = "returns a string"
  value       = data.aws_qldb_ledger.this.id
}

output "this" {
  value = aws_qldb_ledger.this
}
```

[top](#index)