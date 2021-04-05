# google_kms_key_ring

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
module "google_kms_key_ring" {
  source = "./modules/google/d/google_kms_key_ring"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required) - The location for the KeyRing.\nA full list of valid locations can be found by running 'gcloud kms locations list'."
  type        = string
}

variable "name" {
  description = "(required) - The resource name for the KeyRing."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_kms_key_ring" "this" {
  location = var.location
  name     = var.name
  project  = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_kms_key_ring.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_kms_key_ring.this.self_link
}

output "this" {
  value = google_kms_key_ring.this
}
```

[top](#index)