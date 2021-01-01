# aws_kms_ciphertext

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
module "aws_kms_ciphertext" {
  source = "./modules/aws/d/aws_kms_ciphertext"

  # context - (optional) is a type of map of string
  context = {}
  # key_id - (required) is a type of string
  key_id = null
  # plaintext - (required) is a type of string
  plaintext = null
}
```

[top](#index)

### Variables

```hcl
variable "context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "key_id" {
  description = "(required)"
  type        = string
}

variable "plaintext" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_kms_ciphertext" "this" {
  context   = var.context
  key_id    = var.key_id
  plaintext = var.plaintext
}
```

[top](#index)

### Outputs

```hcl
output "ciphertext_blob" {
  description = "returns a string"
  value       = data.aws_kms_ciphertext.this.ciphertext_blob
}

output "id" {
  description = "returns a string"
  value       = data.aws_kms_ciphertext.this.id
}

output "this" {
  value = aws_kms_ciphertext.this
}
```

[top](#index)