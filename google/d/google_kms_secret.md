# google_kms_secret

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_secret" {
  source = "./modules/google/d/google_kms_secret"

  # additional_authenticated_data - (optional) is a type of string
  additional_authenticated_data = null
  # ciphertext - (required) is a type of string
  ciphertext = null
  # crypto_key - (required) is a type of string
  crypto_key = null
}
```

[top](#index)

### Variables

```terraform
variable "additional_authenticated_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ciphertext" {
  description = "(required)"
  type        = string
}

variable "crypto_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_kms_secret" "this" {
  # additional_authenticated_data - (optional) is a type of string
  additional_authenticated_data = var.additional_authenticated_data
  # ciphertext - (required) is a type of string
  ciphertext = var.ciphertext
  # crypto_key - (required) is a type of string
  crypto_key = var.crypto_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_kms_secret.this.id
}

output "plaintext" {
  description = "returns a string"
  value       = data.google_kms_secret.this.plaintext
  sensitive   = true
}

output "this" {
  value = google_kms_secret.this
}
```

[top](#index)