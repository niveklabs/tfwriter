# fortios_filefilter_profile

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
module "fortios_filefilter_profile" {
  source = "./modules/fortios/r/fortios_filefilter_profile"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # extended_log - (optional) is a type of string
  extended_log = null
  # feature_set - (optional) is a type of string
  feature_set = null
  # log - (optional) is a type of string
  log = null
  # name - (optional) is a type of string
  name = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # scan_archive_contents - (optional) is a type of string
  scan_archive_contents = null

  rules = [{
    action    = null
    comment   = null
    direction = null
    file_type = [{
      name = null
    }]
    name               = null
    password_protected = null
    protocol           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "feature_set" {
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

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_archive_contents" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action    = string
      comment   = string
      direction = string
      file_type = list(object(
        {
          name = string
        }
      ))
      name               = string
      password_protected = string
      protocol           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_filefilter_profile" "this" {
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  extended_log          = var.extended_log
  feature_set           = var.feature_set
  log                   = var.log
  name                  = var.name
  replacemsg_group      = var.replacemsg_group
  scan_archive_contents = var.scan_archive_contents

  dynamic "rules" {
    for_each = var.rules
    content {
      action             = rules.value["action"]
      comment            = rules.value["comment"]
      direction          = rules.value["direction"]
      name               = rules.value["name"]
      password_protected = rules.value["password_protected"]
      protocol           = rules.value["protocol"]

      dynamic "file_type" {
        for_each = rules.value.file_type
        content {
          name = file_type.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "extended_log" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.extended_log
}

output "feature_set" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.feature_set
}

output "id" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.id
}

output "log" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.log
}

output "name" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.name
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.replacemsg_group
}

output "scan_archive_contents" {
  description = "returns a string"
  value       = fortios_filefilter_profile.this.scan_archive_contents
}

output "this" {
  value = fortios_filefilter_profile.this
}
```

[top](#index)