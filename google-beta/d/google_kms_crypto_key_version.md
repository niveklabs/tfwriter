# google_kms_crypto_key_version

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_crypto_key_version" {
  source = "./modules/google-beta/d/google_kms_crypto_key_version"

  # crypto_key - (required) is a type of string
  crypto_key = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "crypto_key" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_kms_crypto_key_version" "this" {
  crypto_key = var.crypto_key
  version    = var.version
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.google_kms_crypto_key_version.this.algorithm
}

output "id" {
  description = "returns a string"
  value       = data.google_kms_crypto_key_version.this.id
}

output "protection_level" {
  description = "returns a string"
  value       = data.google_kms_crypto_key_version.this.protection_level
}

output "public_key" {
  description = "returns a list of object"
  value       = data.google_kms_crypto_key_version.this.public_key
}

output "state" {
  description = "returns a string"
  value       = data.google_kms_crypto_key_version.this.state
}

output "this" {
  value = google_kms_crypto_key_version.this
}
```

[top](#index)