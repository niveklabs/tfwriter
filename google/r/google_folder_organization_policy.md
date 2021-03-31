# google_folder_organization_policy

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
module "google_folder_organization_policy" {
  source = "./modules/google/r/google_folder_organization_policy"

  # constraint - (required) is a type of string
  constraint = null
  # folder - (required) is a type of string
  folder = null
  # version - (optional) is a type of number
  version = null

  boolean_policy = [{
    enforced = null
  }]

  list_policy = [{
    allow = [{
      all    = null
      values = []
    }]
    deny = [{
      all    = null
      values = []
    }]
    inherit_from_parent = null
    suggested_value     = null
  }]

  restore_policy = [{
    default = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "constraint" {
  description = "(required) - The name of the Constraint the Policy is configuring, for example, serviceuser.services."
  type        = string
}

variable "folder" {
  description = "(required) - The resource name of the folder to set the policy for. Its format is folders/{folder_id}."
  type        = string
}

variable "version" {
  description = "(optional) - Version of the Policy. Default version is 0."
  type        = number
  default     = null
}

variable "boolean_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enforced = bool
    }
  ))
  default = []
}

variable "list_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow = list(object(
        {
          all    = bool
          values = set(string)
        }
      ))
      deny = list(object(
        {
          all    = bool
          values = set(string)
        }
      ))
      inherit_from_parent = bool
      suggested_value     = string
    }
  ))
  default = []
}

variable "restore_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_folder_organization_policy" "this" {
  constraint = var.constraint
  folder     = var.folder
  version    = var.version

  dynamic "boolean_policy" {
    for_each = var.boolean_policy
    content {
      enforced = boolean_policy.value["enforced"]
    }
  }

  dynamic "list_policy" {
    for_each = var.list_policy
    content {
      inherit_from_parent = list_policy.value["inherit_from_parent"]
      suggested_value     = list_policy.value["suggested_value"]

      dynamic "allow" {
        for_each = list_policy.value.allow
        content {
          all    = allow.value["all"]
          values = allow.value["values"]
        }
      }

      dynamic "deny" {
        for_each = list_policy.value.deny
        content {
          all    = deny.value["all"]
          values = deny.value["values"]
        }
      }

    }
  }

  dynamic "restore_policy" {
    for_each = var.restore_policy
    content {
      default = restore_policy.value["default"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_folder_organization_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_folder_organization_policy.this.id
}

output "update_time" {
  description = "returns a string"
  value       = google_folder_organization_policy.this.update_time
}

output "version" {
  description = "returns a number"
  value       = google_folder_organization_policy.this.version
}

output "this" {
  value = google_folder_organization_policy.this
}
```

[top](#index)