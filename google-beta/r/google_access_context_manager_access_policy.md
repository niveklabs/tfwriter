# google_access_context_manager_access_policy

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_access_context_manager_access_policy" {
  source = "./modules/google-beta/r/google_access_context_manager_access_policy"

  # parent - (required) is a type of string
  parent = null
  # title - (required) is a type of string
  title = null

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
variable "parent" {
  description = "(required) - The parent of this AccessPolicy in the Cloud Resource Hierarchy.\nFormat: organizations/{organization_id}"
  type        = string
}

variable "title" {
  description = "(required) - Human readable title. Does not affect behavior."
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
resource "google_access_context_manager_access_policy" "this" {
  parent = var.parent
  title  = var.title

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

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_access_context_manager_access_policy.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_access_context_manager_access_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = google_access_context_manager_access_policy.this.name
}

output "update_time" {
  description = "returns a string"
  value       = google_access_context_manager_access_policy.this.update_time
}

output "this" {
  value = google_access_context_manager_access_policy.this
}
```

[top](#index)