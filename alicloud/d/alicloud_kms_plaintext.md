# alicloud_kms_plaintext

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_plaintext" {
  source = "./modules/alicloud/d/alicloud_kms_plaintext"

  # ciphertext_blob - (required) is a type of string
  ciphertext_blob = null
  # encryption_context - (optional) is a type of map of string
  encryption_context = {}
}
```

[top](#index)

### Variables

```terraform
variable "ciphertext_blob" {
  description = "(required)"
  type        = string
}

variable "encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kms_plaintext" "this" {
  ciphertext_blob    = var.ciphertext_blob
  encryption_context = var.encryption_context
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kms_plaintext.this.id
}

output "key_id" {
  description = "returns a string"
  value       = data.alicloud_kms_plaintext.this.key_id
}

output "plaintext" {
  description = "returns a string"
  value       = data.alicloud_kms_plaintext.this.plaintext
}

output "this" {
  value = alicloud_kms_plaintext.this
}
```

[top](#index)