# signalfx_dashboard_group

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_dashboard_group" {
  source = "./modules/signalfx/r/signalfx_dashboard_group"

  # authorized_writer_teams - (optional) is a type of set of string
  authorized_writer_teams = []
  # authorized_writer_users - (optional) is a type of set of string
  authorized_writer_users = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # teams - (optional) is a type of list of string
  teams = []

  dashboard = [{
    dashboard_id         = null
    description_override = null
    filter_override = [{
      negated  = null
      property = null
      values   = []
    }]
    name_override = null
    variable_override = [{
      property         = null
      values           = []
      values_suggested = []
    }]
  }]

  import_qualifier = [{
    filters = [{
      negated  = null
      property = null
      values   = []
    }]
    metric = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorized_writer_teams" {
  description = "(optional) - Team IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "authorized_writer_users" {
  description = "(optional) - User IDs that have write access to this dashboard"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of the dashboard group"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the dashboard group"
  type        = string
}

variable "teams" {
  description = "(optional) - Team IDs to associate the dashboard group to"
  type        = list(string)
  default     = null
}

variable "dashboard" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dashboard_id         = string
      description_override = string
      filter_override = set(object(
        {
          negated  = bool
          property = string
          values   = set(string)
        }
      ))
      name_override = string
      variable_override = set(object(
        {
          property         = string
          values           = set(string)
          values_suggested = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "import_qualifier" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      filters = set(object(
        {
          negated  = bool
          property = string
          values   = set(string)
        }
      ))
      metric = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_dashboard_group" "this" {
  authorized_writer_teams = var.authorized_writer_teams
  authorized_writer_users = var.authorized_writer_users
  description             = var.description
  name                    = var.name
  teams                   = var.teams

  dynamic "dashboard" {
    for_each = var.dashboard
    content {
      dashboard_id         = dashboard.value["dashboard_id"]
      description_override = dashboard.value["description_override"]
      name_override        = dashboard.value["name_override"]

      dynamic "filter_override" {
        for_each = dashboard.value.filter_override
        content {
          negated  = filter_override.value["negated"]
          property = filter_override.value["property"]
          values   = filter_override.value["values"]
        }
      }

      dynamic "variable_override" {
        for_each = dashboard.value.variable_override
        content {
          property         = variable_override.value["property"]
          values           = variable_override.value["values"]
          values_suggested = variable_override.value["values_suggested"]
        }
      }

    }
  }

  dynamic "import_qualifier" {
    for_each = var.import_qualifier
    content {
      metric = import_qualifier.value["metric"]

      dynamic "filters" {
        for_each = import_qualifier.value.filters
        content {
          negated  = filters.value["negated"]
          property = filters.value["property"]
          values   = filters.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_dashboard_group.this.id
}

output "this" {
  value = signalfx_dashboard_group.this
}
```

[top](#index)