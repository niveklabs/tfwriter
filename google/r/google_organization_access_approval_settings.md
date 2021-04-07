# google_organization_access_approval_settings

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
module "google_organization_access_approval_settings" {
  source = "./modules/google/r/google_organization_access_approval_settings"

  # notification_emails - (optional) is a type of set of string
  notification_emails = []
  # organization_id - (required) is a type of string
  organization_id = null

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

```terraform
variable "notification_emails" {
  description = "(optional) - A list of email addresses to which notifications relating to approval requests should be sent.\nNotifications relating to a resource will be sent to all emails in the settings of ancestor\nresources of that resource. A maximum of 50 email addresses are allowed."
  type        = set(string)
  default     = null
}

variable "organization_id" {
  description = "(required) - ID of the organization of the access approval settings."
  type        = string
}

variable "enrolled_services" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      cloud_product    = string
      enrollment_level = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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

```terraform
resource "google_organization_access_approval_settings" "this" {
  # notification_emails - (optional) is a type of set of string
  notification_emails = var.notification_emails
  # organization_id - (required) is a type of string
  organization_id = var.organization_id

  dynamic "enrolled_services" {
    for_each = var.enrolled_services
    content {
      # cloud_product - (required) is a type of string
      cloud_product = enrolled_services.value["cloud_product"]
      # enrollment_level - (optional) is a type of string
      enrollment_level = enrolled_services.value["enrollment_level"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "enrolled_ancestor" {
  description = "returns a bool"
  value       = google_organization_access_approval_settings.this.enrolled_ancestor
}

output "id" {
  description = "returns a string"
  value       = google_organization_access_approval_settings.this.id
}

output "name" {
  description = "returns a string"
  value       = google_organization_access_approval_settings.this.name
}

output "notification_emails" {
  description = "returns a set of string"
  value       = google_organization_access_approval_settings.this.notification_emails
}

output "this" {
  value = google_organization_access_approval_settings.this
}
```

[top](#index)