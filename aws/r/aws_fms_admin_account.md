# aws_fms_admin_account

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
module "aws_fms_admin_account" {
  source = "./modules/aws/r/aws_fms_admin_account"

  # account_id - (optional) is a type of string
  account_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_fms_admin_account" "this" {
  account_id = var.account_id
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = aws_fms_admin_account.this.account_id
}

output "id" {
  description = "returns a string"
  value       = aws_fms_admin_account.this.id
}

output "this" {
  value = aws_fms_admin_account.this
}
```

[top](#index)