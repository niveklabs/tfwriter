# google_storage_default_object_acl

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_storage_default_object_acl" {
  source = "./modules/google/r/google_storage_default_object_acl"

  # bucket - (required) is a type of string
  bucket = null
  # role_entity - (optional) is a type of set of string
  role_entity = []
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "role_entity" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_default_object_acl" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # role_entity - (optional) is a type of set of string
  role_entity = var.role_entity
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_storage_default_object_acl.this.id
}

output "role_entity" {
  description = "returns a set of string"
  value       = google_storage_default_object_acl.this.role_entity
}

output "this" {
  value = google_storage_default_object_acl.this
}
```

[top](#index)