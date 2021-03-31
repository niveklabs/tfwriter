# aws_kms_ciphertext

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
module "aws_kms_ciphertext" {
  source = "./modules/aws/r/aws_kms_ciphertext"

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

```terraform
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

### Resource

```terraform
resource "aws_kms_ciphertext" "this" {
  context   = var.context
  key_id    = var.key_id
  plaintext = var.plaintext
}
```

[top](#index)

### Outputs

```terraform
output "ciphertext_blob" {
  description = "returns a string"
  value       = aws_kms_ciphertext.this.ciphertext_blob
}

output "id" {
  description = "returns a string"
  value       = aws_kms_ciphertext.this.id
}

output "this" {
  value = aws_kms_ciphertext.this
}
```

[top](#index)