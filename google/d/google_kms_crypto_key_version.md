# google_kms_crypto_key_version

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_kms_crypto_key_version" {
  source = "./modules/google/d/google_kms_crypto_key_version"

  # crypto_key - (required) is a type of string
  crypto_key = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```hcl
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

```hcl
data "google_kms_crypto_key_version" "this" {
  crypto_key = var.crypto_key
  version    = var.version
}
```

[top](#index)

### Outputs

```hcl
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