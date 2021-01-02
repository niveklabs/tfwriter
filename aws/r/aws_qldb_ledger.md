# aws_qldb_ledger

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
module "aws_qldb_ledger" {
  source = "./modules/aws/r/aws_qldb_ledger"

  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "aws_qldb_ledger" "this" {
  deletion_protection = var.deletion_protection
  name                = var.name
  tags                = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_qldb_ledger.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_qldb_ledger.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_qldb_ledger.this.name
}

output "this" {
  value = aws_qldb_ledger.this
}
```

[top](#index)