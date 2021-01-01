# google_compute_resource_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_compute_resource_policy" {
  source = "./modules/google/r/google_compute_resource_policy"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  group_placement_policy = [{
    availability_domain_count = null
    collocation               = null
    vm_count                  = null
  }]

  snapshot_schedule_policy = [{
    retention_policy = [{
      max_retention_days    = null
      on_source_disk_delete = null
    }]
    schedule = [{
      daily_schedule = [{
        days_in_cycle = null
        start_time    = null
      }]
      hourly_schedule = [{
        hours_in_cycle = null
        start_time     = null
      }]
      weekly_schedule = [{
        day_of_weeks = [{
          day        = null
          start_time = null
        }]
      }]
    }]
    snapshot_properties = [{
      guest_flush       = null
      labels            = {}
      storage_locations = []
    }]
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required) - The name of the resource, provided by the client when initially creating\nthe resource. The resource name must be 1-63 characters long, and comply\nwith RFC1035. Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])'? which means the\nfirst character must be a lowercase letter, and all following characters\nmust be a dash, lowercase letter, or digit, except the last character,\nwhich cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where resource policy resides."
  type        = string
  default     = null
}

variable "group_placement_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_domain_count = number
      collocation               = string
      vm_count                  = number
    }
  ))
  default = []
}

variable "snapshot_schedule_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      retention_policy = list(object(
        {
          max_retention_days    = number
          on_source_disk_delete = string
        }
      ))
      schedule = list(object(
        {
          daily_schedule = list(object(
            {
              days_in_cycle = number
              start_time    = string
            }
          ))
          hourly_schedule = list(object(
            {
              hours_in_cycle = number
              start_time     = string
            }
          ))
          weekly_schedule = list(object(
            {
              day_of_weeks = set(object(
                {
                  day        = string
                  start_time = string
                }
              ))
            }
          ))
        }
      ))
      snapshot_properties = list(object(
        {
          guest_flush       = bool
          labels            = map(string)
          storage_locations = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_compute_resource_policy" "this" {
  name    = var.name
  project = var.project
  region  = var.region

  dynamic "group_placement_policy" {
    for_each = var.group_placement_policy
    content {
      availability_domain_count = group_placement_policy.value["availability_domain_count"]
      collocation               = group_placement_policy.value["collocation"]
      vm_count                  = group_placement_policy.value["vm_count"]
    }
  }

  dynamic "snapshot_schedule_policy" {
    for_each = var.snapshot_schedule_policy
    content {

      dynamic "retention_policy" {
        for_each = snapshot_schedule_policy.value.retention_policy
        content {
          max_retention_days    = retention_policy.value["max_retention_days"]
          on_source_disk_delete = retention_policy.value["on_source_disk_delete"]
        }
      }

      dynamic "schedule" {
        for_each = snapshot_schedule_policy.value.schedule
        content {

          dynamic "daily_schedule" {
            for_each = schedule.value.daily_schedule
            content {
              days_in_cycle = daily_schedule.value["days_in_cycle"]
              start_time    = daily_schedule.value["start_time"]
            }
          }

          dynamic "hourly_schedule" {
            for_each = schedule.value.hourly_schedule
            content {
              hours_in_cycle = hourly_schedule.value["hours_in_cycle"]
              start_time     = hourly_schedule.value["start_time"]
            }
          }

          dynamic "weekly_schedule" {
            for_each = schedule.value.weekly_schedule
            content {

              dynamic "day_of_weeks" {
                for_each = weekly_schedule.value.day_of_weeks
                content {
                  day        = day_of_weeks.value["day"]
                  start_time = day_of_weeks.value["start_time"]
                }
              }

            }
          }

        }
      }

      dynamic "snapshot_properties" {
        for_each = snapshot_schedule_policy.value.snapshot_properties
        content {
          guest_flush       = snapshot_properties.value["guest_flush"]
          labels            = snapshot_properties.value["labels"]
          storage_locations = snapshot_properties.value["storage_locations"]
        }
      }

    }
  }

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_compute_resource_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_resource_policy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_resource_policy.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_resource_policy.this.self_link
}

output "this" {
  value = google_compute_resource_policy.this
}
```

[top](#index)