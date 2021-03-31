# google_kms_secret_asymmetric

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_secret_asymmetric" {
  source = "./modules/google/d/google_kms_secret_asymmetric"

  # ciphertext - (required) is a type of string
  ciphertext = null
  # crc32 - (optional) is a type of string
  crc32 = null
  # crypto_key_version - (required) is a type of string
  crypto_key_version = null
}
```

[top](#index)

### Variables

```terraform
variable "ciphertext" {
  description = "(required) - The public key encrypted ciphertext in base64 encoding"
  type        = string
}

variable "crc32" {
  description = "(optional) - The crc32 checksum of the ciphertext, hexadecimal encoding"
  type        = string
  default     = null
}

variable "crypto_key_version" {
  description = "(required) - The fully qualified KMS crypto key version name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_kms_secret_asymmetric" "this" {
  ciphertext         = var.ciphertext
  crc32              = var.crc32
  crypto_key_version = var.crypto_key_version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_kms_secret_asymmetric.this.id
}

output "plaintext" {
  description = "returns a string"
  value       = data.google_kms_secret_asymmetric.this.plaintext
  sensitive   = true
}

output "this" {
  value = google_kms_secret_asymmetric.this
}
```

[top](#index)