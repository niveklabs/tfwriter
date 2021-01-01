# google_project_access_approval_settings

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_project_access_approval_settings" {
  source = "./modules/google/r/google_project_access_approval_settings"

  # notification_emails - (optional) is a type of set of string
  notification_emails = []
  # project - (optional) is a type of string
  project = null
  # project_id - (required) is a type of string
  project_id = null

  enrolled_services = [{
    cloud_product    = null
    enrollment_level = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "notification_emails" {
  description = "(optional) - A list of email addresses to which notifications relating to approval requests should be sent.\nNotifications relating to a resource will be sent to all emails in the settings of ancestor\nresources of that resource. A maximum of 50 email addresses are allowed."
  type        = set(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - ID of the project of the access approval settings."
  type        = string
}

variable "enrolled_services" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      cloud_product    = string
      enrollment_level = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_project_access_approval_settings" "this" {
  notification_emails = var.notification_emails
  project             = var.project
  project_id          = var.project_id

  dynamic "enrolled_services" {
    for_each = var.enrolled_services
    content {
      cloud_product    = enrolled_services.value["cloud_product"]
      enrollment_level = enrolled_services.value["enrollment_level"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "enrolled_ancestor" {
  description = "returns a bool"
  value       = google_project_access_approval_settings.this.enrolled_ancestor
}

output "id" {
  description = "returns a string"
  value       = google_project_access_approval_settings.this.id
}

output "name" {
  description = "returns a string"
  value       = google_project_access_approval_settings.this.name
}

output "notification_emails" {
  description = "returns a set of string"
  value       = google_project_access_approval_settings.this.notification_emails
}

output "project" {
  description = "returns a string"
  value       = google_project_access_approval_settings.this.project
}

output "this" {
  value = google_project_access_approval_settings.this
}
```

[top](#index)