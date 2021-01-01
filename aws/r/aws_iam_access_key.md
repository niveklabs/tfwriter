# aws_iam_access_key

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
module "aws_iam_access_key" {
  source = "./modules/aws/r/aws_iam_access_key"

  # pgp_key - (optional) is a type of string
  pgp_key = null
  # status - (optional) is a type of string
  status = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```hcl
variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_iam_access_key" "this" {
  pgp_key = var.pgp_key
  status  = var.status
  user    = var.user
}
```

[top](#index)

### Outputs

```hcl
output "encrypted_secret" {
  description = "returns a string"
  value       = aws_iam_access_key.this.encrypted_secret
}

output "id" {
  description = "returns a string"
  value       = aws_iam_access_key.this.id
}

output "key_fingerprint" {
  description = "returns a string"
  value       = aws_iam_access_key.this.key_fingerprint
}

output "secret" {
  description = "returns a string"
  value       = aws_iam_access_key.this.secret
  sensitive   = true
}

output "ses_smtp_password_v4" {
  description = "returns a string"
  value       = aws_iam_access_key.this.ses_smtp_password_v4
  sensitive   = true
}

output "status" {
  description = "returns a string"
  value       = aws_iam_access_key.this.status
}

output "this" {
  value = aws_iam_access_key.this
}
```

[top](#index)