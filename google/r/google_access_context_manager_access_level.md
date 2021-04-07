# google_access_context_manager_access_level

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
module "google_access_context_manager_access_level" {
  source = "./modules/google/r/google_access_context_manager_access_level"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent - (required) is a type of string
  parent = null
  # title - (required) is a type of string
  title = null

  basic = [{
    combining_function = null
    conditions = [{
      device_policy = [{
        allowed_device_management_levels = []
        allowed_encryption_statuses      = []
        os_constraints = [{
          minimum_version = null
          os_type         = null
        }]
        require_admin_approval = null
        require_corp_owned     = null
        require_screen_lock    = null
      }]
      ip_subnetworks         = []
      members                = []
      negate                 = null
      regions                = []
      required_access_levels = []
    }]
  }]

  custom = [{
    expr = [{
      description = null
      expression  = null
      location    = null
      title       = null
    }]
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
  description = "(optional) - Description of the AccessLevel and its use. Does not affect behavior."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Resource name for the Access Level. The short_name component must begin\nwith a letter and only include alphanumeric and '_'.\nFormat: accessPolicies/{policy_id}/accessLevels/{short_name}"
  type        = string
}

variable "parent" {
  description = "(required) - The AccessPolicy this AccessLevel lives in.\nFormat: accessPolicies/{policy_id}"
  type        = string
}

variable "title" {
  description = "(required) - Human readable title. Must be unique within the Policy."
  type        = string
}

variable "basic" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      combining_function = string
      conditions = list(object(
        {
          device_policy = list(object(
            {
              allowed_device_management_levels = list(string)
              allowed_encryption_statuses      = list(string)
              os_constraints = list(object(
                {
                  minimum_version = string
                  os_type         = string
                }
              ))
              require_admin_approval = bool
              require_corp_owned     = bool
              require_screen_lock    = bool
            }
          ))
          ip_subnetworks         = list(string)
          members                = list(string)
          negate                 = bool
          regions                = list(string)
          required_access_levels = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "custom" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      expr = list(object(
        {
          description = string
          expression  = string
          location    = string
          title       = string
        }
      ))
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_access_context_manager_access_level" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # parent - (required) is a type of string
  parent = var.parent
  # title - (required) is a type of string
  title = var.title

  dynamic "basic" {
    for_each = var.basic
    content {
      # combining_function - (optional) is a type of string
      combining_function = basic.value["combining_function"]

      dynamic "conditions" {
        for_each = basic.value.conditions
        content {
          # ip_subnetworks - (optional) is a type of list of string
          ip_subnetworks = conditions.value["ip_subnetworks"]
          # members - (optional) is a type of list of string
          members = conditions.value["members"]
          # negate - (optional) is a type of bool
          negate = conditions.value["negate"]
          # regions - (optional) is a type of list of string
          regions = conditions.value["regions"]
          # required_access_levels - (optional) is a type of list of string
          required_access_levels = conditions.value["required_access_levels"]

          dynamic "device_policy" {
            for_each = conditions.value.device_policy
            content {
              # allowed_device_management_levels - (optional) is a type of list of string
              allowed_device_management_levels = device_policy.value["allowed_device_management_levels"]
              # allowed_encryption_statuses - (optional) is a type of list of string
              allowed_encryption_statuses = device_policy.value["allowed_encryption_statuses"]
              # require_admin_approval - (optional) is a type of bool
              require_admin_approval = device_policy.value["require_admin_approval"]
              # require_corp_owned - (optional) is a type of bool
              require_corp_owned = device_policy.value["require_corp_owned"]
              # require_screen_lock - (optional) is a type of bool
              require_screen_lock = device_policy.value["require_screen_lock"]

              dynamic "os_constraints" {
                for_each = device_policy.value.os_constraints
                content {
                  # minimum_version - (optional) is a type of string
                  minimum_version = os_constraints.value["minimum_version"]
                  # os_type - (required) is a type of string
                  os_type = os_constraints.value["os_type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "custom" {
    for_each = var.custom
    content {

      dynamic "expr" {
        for_each = custom.value.expr
        content {
          # description - (optional) is a type of string
          description = expr.value["description"]
          # expression - (required) is a type of string
          expression = expr.value["expression"]
          # location - (optional) is a type of string
          location = expr.value["location"]
          # title - (optional) is a type of string
          title = expr.value["title"]
        }
      }

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
output "id" {
  description = "returns a string"
  value       = google_access_context_manager_access_level.this.id
}

output "this" {
  value = google_access_context_manager_access_level.this
}
```

[top](#index)