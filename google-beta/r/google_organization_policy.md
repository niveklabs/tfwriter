# google_organization_policy

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
module "google_organization_policy" {
  source = "./modules/google-beta/r/google_organization_policy"

  # constraint - (required) is a type of string
  constraint = null
  # org_id - (required) is a type of string
  org_id = null
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

variable "org_id" {
  description = "(required)"
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
resource "google_organization_policy" "this" {
  # constraint - (required) is a type of string
  constraint = var.constraint
  # org_id - (required) is a type of string
  org_id = var.org_id
  # version - (optional) is a type of number
  version = var.version

  dynamic "boolean_policy" {
    for_each = var.boolean_policy
    content {
      # enforced - (required) is a type of bool
      enforced = boolean_policy.value["enforced"]
    }
  }

  dynamic "list_policy" {
    for_each = var.list_policy
    content {
      # inherit_from_parent - (optional) is a type of bool
      inherit_from_parent = list_policy.value["inherit_from_parent"]
      # suggested_value - (optional) is a type of string
      suggested_value = list_policy.value["suggested_value"]

      dynamic "allow" {
        for_each = list_policy.value.allow
        content {
          # all - (optional) is a type of bool
          all = allow.value["all"]
          # values - (optional) is a type of set of string
          values = allow.value["values"]
        }
      }

      dynamic "deny" {
        for_each = list_policy.value.deny
        content {
          # all - (optional) is a type of bool
          all = deny.value["all"]
          # values - (optional) is a type of set of string
          values = deny.value["values"]
        }
      }

    }
  }

  dynamic "restore_policy" {
    for_each = var.restore_policy
    content {
      # default - (required) is a type of bool
      default = restore_policy.value["default"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = google_organization_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_organization_policy.this.id
}

output "update_time" {
  description = "returns a string"
  value       = google_organization_policy.this.update_time
}

output "version" {
  description = "returns a number"
  value       = google_organization_policy.this.version
}

output "this" {
  value = google_organization_policy.this
}
```

[top](#index)