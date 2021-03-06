# google_monitoring_group

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
module "google_monitoring_group" {
  source = "./modules/google/r/google_monitoring_group"

  # display_name - (required) is a type of string
  display_name = null
  # filter - (required) is a type of string
  filter = null
  # is_cluster - (optional) is a type of bool
  is_cluster = null
  # parent_name - (optional) is a type of string
  parent_name = null
  # project - (optional) is a type of string
  project = null

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
variable "display_name" {
  description = "(required) - A user-assigned name for this group, used only for display\npurposes."
  type        = string
}

variable "filter" {
  description = "(required) - The filter used to determine which monitored resources\nbelong to this group."
  type        = string
}

variable "is_cluster" {
  description = "(optional) - If true, the members of this group are considered to be a\ncluster. The system can perform additional analysis on\ngroups that are clusters."
  type        = bool
  default     = null
}

variable "parent_name" {
  description = "(optional) - The name of the group's parent, if it has one. The format is\n\"projects/{project_id_or_number}/groups/{group_id}\". For\ngroups with no parent, parentName is the empty string, \"\"."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "google_monitoring_group" "this" {
  # display_name - (required) is a type of string
  display_name = var.display_name
  # filter - (required) is a type of string
  filter = var.filter
  # is_cluster - (optional) is a type of bool
  is_cluster = var.is_cluster
  # parent_name - (optional) is a type of string
  parent_name = var.parent_name
  # project - (optional) is a type of string
  project = var.project

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
  value       = google_monitoring_group.this.id
}

output "name" {
  description = "returns a string"
  value       = google_monitoring_group.this.name
}

output "project" {
  description = "returns a string"
  value       = google_monitoring_group.this.project
}

output "this" {
  value = google_monitoring_group.this
}
```

[top](#index)