# google_os_config_patch_deployment

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
module "google_os_config_patch_deployment" {
  source = "./modules/google/r/google_os_config_patch_deployment"

  # description - (optional) is a type of string
  description = null
  # duration - (optional) is a type of string
  duration = null
  # patch_deployment_id - (required) is a type of string
  patch_deployment_id = null
  # project - (optional) is a type of string
  project = null

  instance_filter = [{
    all = null
    group_labels = [{
      labels = {}
    }]
    instance_name_prefixes = []
    instances              = []
    zones                  = []
  }]

  one_time_schedule = [{
    execute_time = null
  }]

  patch_config = [{
    apt = [{
      excludes           = []
      exclusive_packages = []
      type               = null
    }]
    goo = [{
      enabled = null
    }]
    post_step = [{
      linux_exec_step_config = [{
        allowed_success_codes = []
        gcs_object = [{
          bucket            = null
          generation_number = null
          object            = null
        }]
        interpreter = null
        local_path  = null
      }]
      windows_exec_step_config = [{
        allowed_success_codes = []
        gcs_object = [{
          bucket            = null
          generation_number = null
          object            = null
        }]
        interpreter = null
        local_path  = null
      }]
    }]
    pre_step = [{
      linux_exec_step_config = [{
        allowed_success_codes = []
        gcs_object = [{
          bucket            = null
          generation_number = null
          object            = null
        }]
        interpreter = null
        local_path  = null
      }]
      windows_exec_step_config = [{
        allowed_success_codes = []
        gcs_object = [{
          bucket            = null
          generation_number = null
          object            = null
        }]
        interpreter = null
        local_path  = null
      }]
    }]
    reboot_config = null
    windows_update = [{
      classifications   = []
      excludes          = []
      exclusive_patches = []
    }]
    yum = [{
      excludes           = []
      exclusive_packages = []
      minimal            = null
      security           = null
    }]
    zypper = [{
      categories        = []
      excludes          = []
      exclusive_patches = []
      severities        = []
      with_optional     = null
      with_update       = null
    }]
  }]

  recurring_schedule = [{
    end_time          = null
    last_execute_time = null
    monthly = [{
      month_day = null
      week_day_of_month = [{
        day_of_week  = null
        week_ordinal = null
      }]
    }]
    next_execute_time = null
    start_time        = null
    time_of_day = [{
      hours   = null
      minutes = null
      nanos   = null
      seconds = null
    }]
    time_zone = [{
      id      = null
      version = null
    }]
    weekly = [{
      day_of_week = null
    }]
  }]

  rollout = [{
    disruption_budget = [{
      fixed      = null
      percentage = null
    }]
    mode = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the patch deployment. Length of the description is limited to 1024 characters."
  type        = string
  default     = null
}

variable "duration" {
  description = "(optional) - Duration of the patch. After the duration ends, the patch times out.\nA duration in seconds with up to nine fractional digits, terminated by 's'. Example: \"3.5s\""
  type        = string
  default     = null
}

variable "patch_deployment_id" {
  description = "(required) - A name for the patch deployment in the project. When creating a name the following rules apply:\n* Must contain only lowercase letters, numbers, and hyphens.\n* Must start with a letter.\n* Must be between 1-63 characters.\n* Must end with a number or a letter.\n* Must be unique within the project."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_filter" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      all = bool
      group_labels = list(object(
        {
          labels = map(string)
        }
      ))
      instance_name_prefixes = list(string)
      instances              = list(string)
      zones                  = list(string)
    }
  ))
}

variable "one_time_schedule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      execute_time = string
    }
  ))
  default = []
}

variable "patch_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      apt = list(object(
        {
          excludes           = list(string)
          exclusive_packages = list(string)
          type               = string
        }
      ))
      goo = list(object(
        {
          enabled = bool
        }
      ))
      post_step = list(object(
        {
          linux_exec_step_config = list(object(
            {
              allowed_success_codes = list(number)
              gcs_object = list(object(
                {
                  bucket            = string
                  generation_number = string
                  object            = string
                }
              ))
              interpreter = string
              local_path  = string
            }
          ))
          windows_exec_step_config = list(object(
            {
              allowed_success_codes = list(number)
              gcs_object = list(object(
                {
                  bucket            = string
                  generation_number = string
                  object            = string
                }
              ))
              interpreter = string
              local_path  = string
            }
          ))
        }
      ))
      pre_step = list(object(
        {
          linux_exec_step_config = list(object(
            {
              allowed_success_codes = list(number)
              gcs_object = list(object(
                {
                  bucket            = string
                  generation_number = string
                  object            = string
                }
              ))
              interpreter = string
              local_path  = string
            }
          ))
          windows_exec_step_config = list(object(
            {
              allowed_success_codes = list(number)
              gcs_object = list(object(
                {
                  bucket            = string
                  generation_number = string
                  object            = string
                }
              ))
              interpreter = string
              local_path  = string
            }
          ))
        }
      ))
      reboot_config = string
      windows_update = list(object(
        {
          classifications   = list(string)
          excludes          = list(string)
          exclusive_patches = list(string)
        }
      ))
      yum = list(object(
        {
          excludes           = list(string)
          exclusive_packages = list(string)
          minimal            = bool
          security           = bool
        }
      ))
      zypper = list(object(
        {
          categories        = list(string)
          excludes          = list(string)
          exclusive_patches = list(string)
          severities        = list(string)
          with_optional     = bool
          with_update       = bool
        }
      ))
    }
  ))
  default = []
}

variable "recurring_schedule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end_time          = string
      last_execute_time = string
      monthly = list(object(
        {
          month_day = number
          week_day_of_month = list(object(
            {
              day_of_week  = string
              week_ordinal = number
            }
          ))
        }
      ))
      next_execute_time = string
      start_time        = string
      time_of_day = list(object(
        {
          hours   = number
          minutes = number
          nanos   = number
          seconds = number
        }
      ))
      time_zone = list(object(
        {
          id      = string
          version = string
        }
      ))
      weekly = list(object(
        {
          day_of_week = string
        }
      ))
    }
  ))
  default = []
}

variable "rollout" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disruption_budget = list(object(
        {
          fixed      = number
          percentage = number
        }
      ))
      mode = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_os_config_patch_deployment" "this" {
  # description - (optional) is a type of string
  description = var.description
  # duration - (optional) is a type of string
  duration = var.duration
  # patch_deployment_id - (required) is a type of string
  patch_deployment_id = var.patch_deployment_id
  # project - (optional) is a type of string
  project = var.project

  dynamic "instance_filter" {
    for_each = var.instance_filter
    content {
      # all - (optional) is a type of bool
      all = instance_filter.value["all"]
      # instance_name_prefixes - (optional) is a type of list of string
      instance_name_prefixes = instance_filter.value["instance_name_prefixes"]
      # instances - (optional) is a type of list of string
      instances = instance_filter.value["instances"]
      # zones - (optional) is a type of list of string
      zones = instance_filter.value["zones"]

      dynamic "group_labels" {
        for_each = instance_filter.value.group_labels
        content {
          # labels - (required) is a type of map of string
          labels = group_labels.value["labels"]
        }
      }

    }
  }

  dynamic "one_time_schedule" {
    for_each = var.one_time_schedule
    content {
      # execute_time - (required) is a type of string
      execute_time = one_time_schedule.value["execute_time"]
    }
  }

  dynamic "patch_config" {
    for_each = var.patch_config
    content {
      # reboot_config - (optional) is a type of string
      reboot_config = patch_config.value["reboot_config"]

      dynamic "apt" {
        for_each = patch_config.value.apt
        content {
          # excludes - (optional) is a type of list of string
          excludes = apt.value["excludes"]
          # exclusive_packages - (optional) is a type of list of string
          exclusive_packages = apt.value["exclusive_packages"]
          # type - (optional) is a type of string
          type = apt.value["type"]
        }
      }

      dynamic "goo" {
        for_each = patch_config.value.goo
        content {
          # enabled - (required) is a type of bool
          enabled = goo.value["enabled"]
        }
      }

      dynamic "post_step" {
        for_each = patch_config.value.post_step
        content {

          dynamic "linux_exec_step_config" {
            for_each = post_step.value.linux_exec_step_config
            content {
              # allowed_success_codes - (optional) is a type of list of number
              allowed_success_codes = linux_exec_step_config.value["allowed_success_codes"]
              # interpreter - (optional) is a type of string
              interpreter = linux_exec_step_config.value["interpreter"]
              # local_path - (optional) is a type of string
              local_path = linux_exec_step_config.value["local_path"]

              dynamic "gcs_object" {
                for_each = linux_exec_step_config.value.gcs_object
                content {
                  # bucket - (required) is a type of string
                  bucket = gcs_object.value["bucket"]
                  # generation_number - (required) is a type of string
                  generation_number = gcs_object.value["generation_number"]
                  # object - (required) is a type of string
                  object = gcs_object.value["object"]
                }
              }

            }
          }

          dynamic "windows_exec_step_config" {
            for_each = post_step.value.windows_exec_step_config
            content {
              # allowed_success_codes - (optional) is a type of list of number
              allowed_success_codes = windows_exec_step_config.value["allowed_success_codes"]
              # interpreter - (optional) is a type of string
              interpreter = windows_exec_step_config.value["interpreter"]
              # local_path - (optional) is a type of string
              local_path = windows_exec_step_config.value["local_path"]

              dynamic "gcs_object" {
                for_each = windows_exec_step_config.value.gcs_object
                content {
                  # bucket - (required) is a type of string
                  bucket = gcs_object.value["bucket"]
                  # generation_number - (required) is a type of string
                  generation_number = gcs_object.value["generation_number"]
                  # object - (required) is a type of string
                  object = gcs_object.value["object"]
                }
              }

            }
          }

        }
      }

      dynamic "pre_step" {
        for_each = patch_config.value.pre_step
        content {

          dynamic "linux_exec_step_config" {
            for_each = pre_step.value.linux_exec_step_config
            content {
              # allowed_success_codes - (optional) is a type of list of number
              allowed_success_codes = linux_exec_step_config.value["allowed_success_codes"]
              # interpreter - (optional) is a type of string
              interpreter = linux_exec_step_config.value["interpreter"]
              # local_path - (optional) is a type of string
              local_path = linux_exec_step_config.value["local_path"]

              dynamic "gcs_object" {
                for_each = linux_exec_step_config.value.gcs_object
                content {
                  # bucket - (required) is a type of string
                  bucket = gcs_object.value["bucket"]
                  # generation_number - (required) is a type of string
                  generation_number = gcs_object.value["generation_number"]
                  # object - (required) is a type of string
                  object = gcs_object.value["object"]
                }
              }

            }
          }

          dynamic "windows_exec_step_config" {
            for_each = pre_step.value.windows_exec_step_config
            content {
              # allowed_success_codes - (optional) is a type of list of number
              allowed_success_codes = windows_exec_step_config.value["allowed_success_codes"]
              # interpreter - (optional) is a type of string
              interpreter = windows_exec_step_config.value["interpreter"]
              # local_path - (optional) is a type of string
              local_path = windows_exec_step_config.value["local_path"]

              dynamic "gcs_object" {
                for_each = windows_exec_step_config.value.gcs_object
                content {
                  # bucket - (required) is a type of string
                  bucket = gcs_object.value["bucket"]
                  # generation_number - (required) is a type of string
                  generation_number = gcs_object.value["generation_number"]
                  # object - (required) is a type of string
                  object = gcs_object.value["object"]
                }
              }

            }
          }

        }
      }

      dynamic "windows_update" {
        for_each = patch_config.value.windows_update
        content {
          # classifications - (optional) is a type of list of string
          classifications = windows_update.value["classifications"]
          # excludes - (optional) is a type of list of string
          excludes = windows_update.value["excludes"]
          # exclusive_patches - (optional) is a type of list of string
          exclusive_patches = windows_update.value["exclusive_patches"]
        }
      }

      dynamic "yum" {
        for_each = patch_config.value.yum
        content {
          # excludes - (optional) is a type of list of string
          excludes = yum.value["excludes"]
          # exclusive_packages - (optional) is a type of list of string
          exclusive_packages = yum.value["exclusive_packages"]
          # minimal - (optional) is a type of bool
          minimal = yum.value["minimal"]
          # security - (optional) is a type of bool
          security = yum.value["security"]
        }
      }

      dynamic "zypper" {
        for_each = patch_config.value.zypper
        content {
          # categories - (optional) is a type of list of string
          categories = zypper.value["categories"]
          # excludes - (optional) is a type of list of string
          excludes = zypper.value["excludes"]
          # exclusive_patches - (optional) is a type of list of string
          exclusive_patches = zypper.value["exclusive_patches"]
          # severities - (optional) is a type of list of string
          severities = zypper.value["severities"]
          # with_optional - (optional) is a type of bool
          with_optional = zypper.value["with_optional"]
          # with_update - (optional) is a type of bool
          with_update = zypper.value["with_update"]
        }
      }

    }
  }

  dynamic "recurring_schedule" {
    for_each = var.recurring_schedule
    content {
      # end_time - (optional) is a type of string
      end_time = recurring_schedule.value["end_time"]
      # start_time - (optional) is a type of string
      start_time = recurring_schedule.value["start_time"]

      dynamic "monthly" {
        for_each = recurring_schedule.value.monthly
        content {
          # month_day - (optional) is a type of number
          month_day = monthly.value["month_day"]

          dynamic "week_day_of_month" {
            for_each = monthly.value.week_day_of_month
            content {
              # day_of_week - (required) is a type of string
              day_of_week = week_day_of_month.value["day_of_week"]
              # week_ordinal - (required) is a type of number
              week_ordinal = week_day_of_month.value["week_ordinal"]
            }
          }

        }
      }

      dynamic "time_of_day" {
        for_each = recurring_schedule.value.time_of_day
        content {
          # hours - (optional) is a type of number
          hours = time_of_day.value["hours"]
          # minutes - (optional) is a type of number
          minutes = time_of_day.value["minutes"]
          # nanos - (optional) is a type of number
          nanos = time_of_day.value["nanos"]
          # seconds - (optional) is a type of number
          seconds = time_of_day.value["seconds"]
        }
      }

      dynamic "time_zone" {
        for_each = recurring_schedule.value.time_zone
        content {
          # id - (required) is a type of string
          id = time_zone.value["id"]
          # version - (optional) is a type of string
          version = time_zone.value["version"]
        }
      }

      dynamic "weekly" {
        for_each = recurring_schedule.value.weekly
        content {
          # day_of_week - (required) is a type of string
          day_of_week = weekly.value["day_of_week"]
        }
      }

    }
  }

  dynamic "rollout" {
    for_each = var.rollout
    content {
      # mode - (required) is a type of string
      mode = rollout.value["mode"]

      dynamic "disruption_budget" {
        for_each = rollout.value.disruption_budget
        content {
          # fixed - (optional) is a type of number
          fixed = disruption_budget.value["fixed"]
          # percentage - (optional) is a type of number
          percentage = disruption_budget.value["percentage"]
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.id
}

output "last_execute_time" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.last_execute_time
}

output "name" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.name
}

output "project" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.project
}

output "update_time" {
  description = "returns a string"
  value       = google_os_config_patch_deployment.this.update_time
}

output "this" {
  value = google_os_config_patch_deployment.this
}
```

[top](#index)