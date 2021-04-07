# fortios_sshfilter_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_sshfilter_profile" {
  source = "./modules/fortios/r/fortios_sshfilter_profile"

  # block - (optional) is a type of string
  block = null
  # default_command_log - (optional) is a type of string
  default_command_log = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # log - (optional) is a type of string
  log = null
  # name - (optional) is a type of string
  name = null

  file_filter = [{
    entries = [{
      action    = null
      comment   = null
      direction = null
      file_type = [{
        name = null
      }]
      filter             = null
      password_protected = null
    }]
    log                   = null
    scan_archive_contents = null
    status                = null
  }]

  shell_commands = [{
    action   = null
    alert    = null
    id       = null
    log      = null
    pattern  = null
    severity = null
    type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_command_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      entries = list(object(
        {
          action    = string
          comment   = string
          direction = string
          file_type = list(object(
            {
              name = string
            }
          ))
          filter             = string
          password_protected = string
        }
      ))
      log                   = string
      scan_archive_contents = string
      status                = string
    }
  ))
  default = []
}

variable "shell_commands" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      alert    = string
      id       = number
      log      = string
      pattern  = string
      severity = string
      type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_sshfilter_profile" "this" {
  # block - (optional) is a type of string
  block = var.block
  # default_command_log - (optional) is a type of string
  default_command_log = var.default_command_log
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # log - (optional) is a type of string
  log = var.log
  # name - (optional) is a type of string
  name = var.name

  dynamic "file_filter" {
    for_each = var.file_filter
    content {
      # log - (optional) is a type of string
      log = file_filter.value["log"]
      # scan_archive_contents - (optional) is a type of string
      scan_archive_contents = file_filter.value["scan_archive_contents"]
      # status - (optional) is a type of string
      status = file_filter.value["status"]

      dynamic "entries" {
        for_each = file_filter.value.entries
        content {
          # action - (optional) is a type of string
          action = entries.value["action"]
          # comment - (optional) is a type of string
          comment = entries.value["comment"]
          # direction - (optional) is a type of string
          direction = entries.value["direction"]
          # filter - (optional) is a type of string
          filter = entries.value["filter"]
          # password_protected - (optional) is a type of string
          password_protected = entries.value["password_protected"]

          dynamic "file_type" {
            for_each = entries.value.file_type
            content {
              # name - (optional) is a type of string
              name = file_type.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "shell_commands" {
    for_each = var.shell_commands
    content {
      # action - (optional) is a type of string
      action = shell_commands.value["action"]
      # alert - (optional) is a type of string
      alert = shell_commands.value["alert"]
      # id - (optional) is a type of number
      id = shell_commands.value["id"]
      # log - (optional) is a type of string
      log = shell_commands.value["log"]
      # pattern - (optional) is a type of string
      pattern = shell_commands.value["pattern"]
      # severity - (optional) is a type of string
      severity = shell_commands.value["severity"]
      # type - (optional) is a type of string
      type = shell_commands.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "block" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.block
}

output "default_command_log" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.default_command_log
}

output "id" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.id
}

output "log" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.log
}

output "name" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.name
}

output "this" {
  value = fortios_sshfilter_profile.this
}
```

[top](#index)