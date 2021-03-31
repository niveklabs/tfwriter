# google_iap_brand

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_iap_brand" {
  source = "./modules/google/r/google_iap_brand"

  # application_title - (required) is a type of string
  application_title = null
  # project - (optional) is a type of string
  project = null
  # support_email - (required) is a type of string
  support_email = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_title" {
  description = "(required) - Application name displayed on OAuth consent screen."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "support_email" {
  description = "(required) - Support email displayed on the OAuth consent screen. Can be either a\nuser or group email. When a user email is specified, the caller must\nbe the user with the associated email address. When a group email is\nspecified, the caller can be either a user or a service account which\nis an owner of the specified group in Cloud Identity."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_iap_brand" "this" {
  application_title = var.application_title
  project           = var.project
  support_email     = var.support_email

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_iap_brand.this.id
}

output "name" {
  description = "returns a string"
  value       = google_iap_brand.this.name
}

output "org_internal_only" {
  description = "returns a bool"
  value       = google_iap_brand.this.org_internal_only
}

output "project" {
  description = "returns a string"
  value       = google_iap_brand.this.project
}

output "this" {
  value = google_iap_brand.this
}
```

[top](#index)