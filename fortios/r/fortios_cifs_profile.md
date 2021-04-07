# fortios_cifs_profile

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
module "fortios_cifs_profile" {
  source = "./modules/fortios/r/fortios_cifs_profile"

  # domain_controller - (optional) is a type of string
  domain_controller = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # server_credential_type - (optional) is a type of string
  server_credential_type = null

  file_filter = [{
    entries = [{
      action    = null
      comment   = null
      direction = null
      file_type = [{
        name = null
      }]
      filter = null
    }]
    log    = null
    status = null
  }]

  server_keytab = [{
    keytab    = null
    principal = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_credential_type" {
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
          filter = string
        }
      ))
      log    = string
      status = string
    }
  ))
  default = []
}

variable "server_keytab" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      keytab    = string
      principal = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_cifs_profile" "this" {
  # domain_controller - (optional) is a type of string
  domain_controller = var.domain_controller
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # server_credential_type - (optional) is a type of string
  server_credential_type = var.server_credential_type

  dynamic "file_filter" {
    for_each = var.file_filter
    content {
      # log - (optional) is a type of string
      log = file_filter.value["log"]
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

  dynamic "server_keytab" {
    for_each = var.server_keytab
    content {
      # keytab - (optional) is a type of string
      keytab = server_keytab.value["keytab"]
      # principal - (optional) is a type of string
      principal = server_keytab.value["principal"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "domain_controller" {
  description = "returns a string"
  value       = fortios_cifs_profile.this.domain_controller
}

output "id" {
  description = "returns a string"
  value       = fortios_cifs_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_cifs_profile.this.name
}

output "server_credential_type" {
  description = "returns a string"
  value       = fortios_cifs_profile.this.server_credential_type
}

output "this" {
  value = fortios_cifs_profile.this
}
```

[top](#index)