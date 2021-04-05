# nutanix_protection_rule

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_protection_rule" {
  source = "./modules/nutanix/r/nutanix_protection_rule"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # start_time - (optional) is a type of string
  start_time = null

  availability_zone_connectivity_list = [{
    destination_availability_zone_index = null
    snapshot_schedule_list = [{
      auto_suspend_timeout_secs = null
      local_snapshot_retention_policy = [{
        num_snapshots                                  = null
        rollup_retention_policy_multiple               = null
        rollup_retention_policy_snapshot_interval_type = null
      }]
      recovery_point_objective_secs = null
      remote_snapshot_retention_policy = [{
        num_snapshots                                  = null
        rollup_retention_policy_multiple               = null
        rollup_retention_policy_snapshot_interval_type = null
      }]
      snapshot_type = null
    }]
    source_availability_zone_index = null
  }]

  categories = [{
    name  = null
    value = null
  }]

  category_filter = [{
    kind_list = []
    params = [{
      name   = null
      values = []
    }]
    type = null
  }]

  ordered_availability_zone_list = [{
    availability_zone_url = null
    cluster_uuid          = null
  }]

  owner_reference = [{
    kind = null
    name = null
    uuid = null
  }]

  project_reference = [{
    kind = null
    name = null
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone_connectivity_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      destination_availability_zone_index = number
      snapshot_schedule_list = list(object(
        {
          auto_suspend_timeout_secs = number
          local_snapshot_retention_policy = list(object(
            {
              num_snapshots                                  = number
              rollup_retention_policy_multiple               = number
              rollup_retention_policy_snapshot_interval_type = string
            }
          ))
          recovery_point_objective_secs = number
          remote_snapshot_retention_policy = list(object(
            {
              num_snapshots                                  = number
              rollup_retention_policy_multiple               = number
              rollup_retention_policy_snapshot_interval_type = string
            }
          ))
          snapshot_type = string
        }
      ))
      source_availability_zone_index = number
    }
  ))
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "category_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind_list = list(string)
      params = set(object(
        {
          name   = string
          values = list(string)
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "ordered_availability_zone_list" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      availability_zone_url = string
      cluster_uuid          = string
    }
  ))
}

variable "owner_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "project_reference" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kind = string
      name = string
      uuid = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_protection_rule" "this" {
  description = var.description
  name        = var.name
  start_time  = var.start_time

  dynamic "availability_zone_connectivity_list" {
    for_each = var.availability_zone_connectivity_list
    content {
      destination_availability_zone_index = availability_zone_connectivity_list.value["destination_availability_zone_index"]
      source_availability_zone_index      = availability_zone_connectivity_list.value["source_availability_zone_index"]

      dynamic "snapshot_schedule_list" {
        for_each = availability_zone_connectivity_list.value.snapshot_schedule_list
        content {
          auto_suspend_timeout_secs     = snapshot_schedule_list.value["auto_suspend_timeout_secs"]
          recovery_point_objective_secs = snapshot_schedule_list.value["recovery_point_objective_secs"]
          snapshot_type                 = snapshot_schedule_list.value["snapshot_type"]

          dynamic "local_snapshot_retention_policy" {
            for_each = snapshot_schedule_list.value.local_snapshot_retention_policy
            content {
              num_snapshots                                  = local_snapshot_retention_policy.value["num_snapshots"]
              rollup_retention_policy_multiple               = local_snapshot_retention_policy.value["rollup_retention_policy_multiple"]
              rollup_retention_policy_snapshot_interval_type = local_snapshot_retention_policy.value["rollup_retention_policy_snapshot_interval_type"]
            }
          }

          dynamic "remote_snapshot_retention_policy" {
            for_each = snapshot_schedule_list.value.remote_snapshot_retention_policy
            content {
              num_snapshots                                  = remote_snapshot_retention_policy.value["num_snapshots"]
              rollup_retention_policy_multiple               = remote_snapshot_retention_policy.value["rollup_retention_policy_multiple"]
              rollup_retention_policy_snapshot_interval_type = remote_snapshot_retention_policy.value["rollup_retention_policy_snapshot_interval_type"]
            }
          }

        }
      }

    }
  }

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

  dynamic "category_filter" {
    for_each = var.category_filter
    content {
      kind_list = category_filter.value["kind_list"]
      type      = category_filter.value["type"]

      dynamic "params" {
        for_each = category_filter.value.params
        content {
          name   = params.value["name"]
          values = params.value["values"]
        }
      }

    }
  }

  dynamic "ordered_availability_zone_list" {
    for_each = var.ordered_availability_zone_list
    content {
      availability_zone_url = ordered_availability_zone_list.value["availability_zone_url"]
      cluster_uuid          = ordered_availability_zone_list.value["cluster_uuid"]
    }
  }

  dynamic "owner_reference" {
    for_each = var.owner_reference
    content {
      kind = owner_reference.value["kind"]
      name = owner_reference.value["name"]
      uuid = owner_reference.value["uuid"]
    }
  }

  dynamic "project_reference" {
    for_each = var.project_reference
    content {
      kind = project_reference.value["kind"]
      name = project_reference.value["name"]
      uuid = project_reference.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_protection_rule.this.api_version
}

output "description" {
  description = "returns a string"
  value       = nutanix_protection_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_protection_rule.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_protection_rule.this.metadata
}

output "start_time" {
  description = "returns a string"
  value       = nutanix_protection_rule.this.start_time
}

output "state" {
  description = "returns a string"
  value       = nutanix_protection_rule.this.state
}

output "this" {
  value = nutanix_protection_rule.this
}
```

[top](#index)