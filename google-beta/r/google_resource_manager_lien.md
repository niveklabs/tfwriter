# google_resource_manager_lien

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
module "google_resource_manager_lien" {
  source = "./modules/google-beta/r/google_resource_manager_lien"

  # origin - (required) is a type of string
  origin = null
  # parent - (required) is a type of string
  parent = null
  # reason - (required) is a type of string
  reason = null
  # restrictions - (required) is a type of list of string
  restrictions = []

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "origin" {
  description = "(required) - A stable, user-visible/meaningful string identifying the origin\nof the Lien, intended to be inspected programmatically. Maximum length of\n200 characters."
  type        = string
}

variable "parent" {
  description = "(required) - A reference to the resource this Lien is attached to.\nThe server will validate the parent against those for which Liens are supported.\nSince a variety of objects can have Liens against them, you must provide the type\nprefix (e.g. \"projects/my-project-name\")."
  type        = string
}

variable "reason" {
  description = "(required) - Concise user-visible strings indicating why an action cannot be performed\non a resource. Maximum length of 200 characters."
  type        = string
}

variable "restrictions" {
  description = "(required) - The types of operations which should be blocked as a result of this Lien.\nEach value should correspond to an IAM permission. The server will validate\nthe permissions against those for which Liens are supported.  An empty\nlist is meaningless and will be rejected.\ne.g. ['resourcemanager.projects.delete']"
  type        = list(string)
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
resource "google_resource_manager_lien" "this" {
  origin       = var.origin
  parent       = var.parent
  reason       = var.reason
  restrictions = var.restrictions

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
output "create_time" {
  description = "returns a string"
  value       = google_resource_manager_lien.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_resource_manager_lien.this.id
}

output "name" {
  description = "returns a string"
  value       = google_resource_manager_lien.this.name
}

output "this" {
  value = google_resource_manager_lien.this
}
```

[top](#index)