# google_storage_bucket_acl

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_storage_bucket_acl" {
  source = "./modules/google-beta/r/google_storage_bucket_acl"

  # bucket - (required) is a type of string
  bucket = null
  # default_acl - (optional) is a type of string
  default_acl = null
  # predefined_acl - (optional) is a type of string
  predefined_acl = null
  # role_entity - (optional) is a type of list of string
  role_entity = []
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - The name of the bucket it applies to."
  type        = string
}

variable "default_acl" {
  description = "(optional) - Configure this ACL to be the default ACL."
  type        = string
  default     = null
}

variable "predefined_acl" {
  description = "(optional) - The canned GCS ACL to apply. Must be set if role_entity is not."
  type        = string
  default     = null
}

variable "role_entity" {
  description = "(optional) - List of role/entity pairs in the form ROLE:entity. See GCS Bucket ACL documentation  for more details. Must be set if predefined_acl is not."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_bucket_acl" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # default_acl - (optional) is a type of string
  default_acl = var.default_acl
  # predefined_acl - (optional) is a type of string
  predefined_acl = var.predefined_acl
  # role_entity - (optional) is a type of list of string
  role_entity = var.role_entity
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_storage_bucket_acl.this.id
}

output "role_entity" {
  description = "returns a list of string"
  value       = google_storage_bucket_acl.this.role_entity
}

output "this" {
  value = google_storage_bucket_acl.this
}
```

[top](#index)