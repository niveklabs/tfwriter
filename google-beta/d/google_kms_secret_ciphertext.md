# google_kms_secret_ciphertext

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
module "google_kms_secret_ciphertext" {
  source = "./modules/google-beta/d/google_kms_secret_ciphertext"

  # crypto_key - (required) is a type of string
  crypto_key = null
  # plaintext - (required) is a type of string
  plaintext = null
}
```

[top](#index)

### Variables

```terraform
variable "crypto_key" {
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

```terraform
data "google_kms_secret_ciphertext" "this" {
  crypto_key = var.crypto_key
  plaintext  = var.plaintext
}
```

[top](#index)

### Outputs

```terraform
output "ciphertext" {
  description = "returns a string"
  value       = data.google_kms_secret_ciphertext.this.ciphertext
}

output "id" {
  description = "returns a string"
  value       = data.google_kms_secret_ciphertext.this.id
}

output "this" {
  value = google_kms_secret_ciphertext.this
}
```

[top](#index)