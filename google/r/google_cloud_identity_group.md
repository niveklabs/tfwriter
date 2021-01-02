# google_cloud_identity_group

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
module "google_cloud_identity_group" {
  source = "./modules/google/r/google_cloud_identity_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (required) is a type of map of string
  labels = {}
  # parent - (required) is a type of string
  parent = null

  group_key = [{
    id        = null
    namespace = null
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
variable "description" {
  description = "(optional) - An extended description to help users determine the purpose of a Group.\nMust not be longer than 4,096 characters."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of the Group."
  type        = string
  default     = null
}

variable "labels" {
  description = "(required) - The labels that apply to the Group.\n\nMust not contain more than one entry. Must contain the entry\n'cloudidentity.googleapis.com/groups.discussion_forum': '' if the Group is a Google Group or\n'system/groups/external': '' if the Group is an external-identity-mapped group."
  type        = map(string)
}

variable "parent" {
  description = "(required) - The resource name of the entity under which this Group resides in the\nCloud Identity resource hierarchy.\n\nMust be of the form identitysources/{identity_source_id} for external-identity-mapped\ngroups or customers/{customer_id} for Google Groups."
  type        = string
}

variable "group_key" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      id        = string
      namespace = string
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

```terraform
resource "google_cloud_identity_group" "this" {
  description  = var.description
  display_name = var.display_name
  labels       = var.labels
  parent       = var.parent

  dynamic "group_key" {
    for_each = var.group_key
    content {
      id        = group_key.value["id"]
      namespace = group_key.value["namespace"]
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
  value       = google_cloud_identity_group.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_cloud_identity_group.this.id
}

output "name" {
  description = "returns a string"
  value       = google_cloud_identity_group.this.name
}

output "update_time" {
  description = "returns a string"
  value       = google_cloud_identity_group.this.update_time
}

output "this" {
  value = google_cloud_identity_group.this
}
```

[top](#index)