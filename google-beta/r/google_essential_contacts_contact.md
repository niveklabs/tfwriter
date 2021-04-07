# google_essential_contacts_contact

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
module "google_essential_contacts_contact" {
  source = "./modules/google-beta/r/google_essential_contacts_contact"

  # email - (required) is a type of string
  email = null
  # language_tag - (required) is a type of string
  language_tag = null
  # notification_category_subscriptions - (required) is a type of list of string
  notification_category_subscriptions = []
  # parent - (required) is a type of string
  parent = null

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
variable "email" {
  description = "(required) - The email address to send notifications to. This does not need to be a Google account."
  type        = string
}

variable "language_tag" {
  description = "(required) - The preferred language for notifications, as a ISO 639-1 language code. See Supported languages for a list of supported languages."
  type        = string
}

variable "notification_category_subscriptions" {
  description = "(required) - The categories of notifications that the contact will receive communications for."
  type        = list(string)
}

variable "parent" {
  description = "(required) - The resource to save this contact for. Format: organizations/{organization_id}, folders/{folder_id} or projects/{project_id}"
  type        = string
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
resource "google_essential_contacts_contact" "this" {
  # email - (required) is a type of string
  email = var.email
  # language_tag - (required) is a type of string
  language_tag = var.language_tag
  # notification_category_subscriptions - (required) is a type of list of string
  notification_category_subscriptions = var.notification_category_subscriptions
  # parent - (required) is a type of string
  parent = var.parent

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
output "id" {
  description = "returns a string"
  value       = google_essential_contacts_contact.this.id
}

output "name" {
  description = "returns a string"
  value       = google_essential_contacts_contact.this.name
}

output "this" {
  value = google_essential_contacts_contact.this
}
```

[top](#index)