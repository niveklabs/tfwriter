# oci_logging_log

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_log" {
  source = "./modules/oci/r/oci_logging_log"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # log_group_id - (required) is a type of string
  log_group_id = null
  # log_type - (required) is a type of string
  log_type = null
  # retention_duration - (optional) is a type of number
  retention_duration = null

  configuration = [{
    compartment_id = null
    source = [{
      category    = null
      resource    = null
      service     = null
      source_type = null
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
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_group_id" {
  description = "(required)"
  type        = string
}

variable "log_type" {
  description = "(required)"
  type        = string
}

variable "retention_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      compartment_id = string
      source = list(object(
        {
          category    = string
          resource    = string
          service     = string
          source_type = string
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
resource "oci_logging_log" "this" {
  defined_tags       = var.defined_tags
  display_name       = var.display_name
  freeform_tags      = var.freeform_tags
  is_enabled         = var.is_enabled
  log_group_id       = var.log_group_id
  log_type           = var.log_type
  retention_duration = var.retention_duration

  dynamic "configuration" {
    for_each = var.configuration
    content {
      compartment_id = configuration.value["compartment_id"]

      dynamic "source" {
        for_each = configuration.value.source
        content {
          category    = source.value["category"]
          resource    = source.value["resource"]
          service     = source.value["service"]
          source_type = source.value["source_type"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_logging_log.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_logging_log.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_logging_log.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_logging_log.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = oci_logging_log.this.is_enabled
}

output "retention_duration" {
  description = "returns a number"
  value       = oci_logging_log.this.retention_duration
}

output "state" {
  description = "returns a string"
  value       = oci_logging_log.this.state
}

output "tenancy_id" {
  description = "returns a string"
  value       = oci_logging_log.this.tenancy_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_logging_log.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = oci_logging_log.this.time_last_modified
}

output "this" {
  value = oci_logging_log.this
}
```

[top](#index)