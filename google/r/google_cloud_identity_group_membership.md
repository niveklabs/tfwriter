# google_cloud_identity_group_membership

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_cloud_identity_group_membership" {
  source = "./modules/google/r/google_cloud_identity_group_membership"

  # group - (required) is a type of string
  group = null

  preferred_member_key = [{
    id        = null
    namespace = null
  }]

  roles = [{
    name = null
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
variable "group" {
  description = "(required) - The name of the Group to create this membership in."
  type        = string
}

variable "preferred_member_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id        = string
      namespace = string
    }
  ))
  default = []
}

variable "roles" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
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
resource "google_cloud_identity_group_membership" "this" {
  group = var.group

  dynamic "preferred_member_key" {
    for_each = var.preferred_member_key
    content {
      id        = preferred_member_key.value["id"]
      namespace = preferred_member_key.value["namespace"]
    }
  }

  dynamic "roles" {
    for_each = var.roles
    content {
      name = roles.value["name"]
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

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_cloud_identity_group_membership.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_cloud_identity_group_membership.this.id
}

output "name" {
  description = "returns a string"
  value       = google_cloud_identity_group_membership.this.name
}

output "type" {
  description = "returns a string"
  value       = google_cloud_identity_group_membership.this.type
}

output "update_time" {
  description = "returns a string"
  value       = google_cloud_identity_group_membership.this.update_time
}

output "this" {
  value = google_cloud_identity_group_membership.this
}
```

[top](#index)