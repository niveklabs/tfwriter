# alicloud_kms_ciphertext

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_ciphertext" {
  source = "./modules/alicloud/r/alicloud_kms_ciphertext"

  # encryption_context - (optional) is a type of map of string
  encryption_context = {}
  # key_id - (required) is a type of string
  key_id = null
  # plaintext - (required) is a type of string
  plaintext = null
}
```

[top](#index)

### Variables

```terraform
variable "encryption_context" {
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
resource "alicloud_kms_ciphertext" "this" {
  encryption_context = var.encryption_context
  key_id             = var.key_id
  plaintext          = var.plaintext
}
```

[top](#index)

### Outputs

```terraform
output "ciphertext_blob" {
  description = "returns a string"
  value       = alicloud_kms_ciphertext.this.ciphertext_blob
}

output "id" {
  description = "returns a string"
  value       = alicloud_kms_ciphertext.this.id
}

output "this" {
  value = alicloud_kms_ciphertext.this
}
```

[top](#index)