# google_kms_crypto_key

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_crypto_key" {
  source = "./modules/google-beta/d/google_kms_crypto_key"

  # key_ring - (required) is a type of string
  key_ring = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "key_ring" {
  description = "(required) - The KeyRing that this key belongs to.\nFormat: ''projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}''."
  type        = string
}

variable "name" {
  description = "(required) - The resource name for the CryptoKey."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_kms_crypto_key" "this" {
  key_ring = var.key_ring
  name     = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_kms_crypto_key.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_kms_crypto_key.this.labels
}

output "purpose" {
  description = "returns a string"
  value       = data.google_kms_crypto_key.this.purpose
}

output "rotation_period" {
  description = "returns a string"
  value       = data.google_kms_crypto_key.this.rotation_period
}

output "self_link" {
  description = "returns a string"
  value       = data.google_kms_crypto_key.this.self_link
}

output "skip_initial_version_creation" {
  description = "returns a bool"
  value       = data.google_kms_crypto_key.this.skip_initial_version_creation
}

output "version_template" {
  description = "returns a list of object"
  value       = data.google_kms_crypto_key.this.version_template
}

output "this" {
  value = google_kms_crypto_key.this
}
```

[top](#index)