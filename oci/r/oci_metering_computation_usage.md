# oci_metering_computation_usage

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_metering_computation_usage" {
  source = "./modules/oci/r/oci_metering_computation_usage"

  # compartment_depth - (optional) is a type of number
  compartment_depth = null
  # filter - (optional) is a type of string
  filter = null
  # granularity - (required) is a type of string
  granularity = null
  # group_by - (optional) is a type of list of string
  group_by = []
  # query_type - (optional) is a type of string
  query_type = null
  # tenant_id - (required) is a type of string
  tenant_id = null
  # time_usage_ended - (required) is a type of string
  time_usage_ended = null
  # time_usage_started - (required) is a type of string
  time_usage_started = null

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
variable "compartment_depth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "granularity" {
  description = "(required)"
  type        = string
}

variable "group_by" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "query_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "time_usage_ended" {
  description = "(required)"
  type        = string
}

variable "time_usage_started" {
  description = "(required)"
  type        = string
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
resource "oci_metering_computation_usage" "this" {
  compartment_depth  = var.compartment_depth
  filter             = var.filter
  granularity        = var.granularity
  group_by           = var.group_by
  query_type         = var.query_type
  tenant_id          = var.tenant_id
  time_usage_ended   = var.time_usage_ended
  time_usage_started = var.time_usage_started

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
output "compartment_depth" {
  description = "returns a number"
  value       = oci_metering_computation_usage.this.compartment_depth
}

output "group_by" {
  description = "returns a list of string"
  value       = oci_metering_computation_usage.this.group_by
}

output "id" {
  description = "returns a string"
  value       = oci_metering_computation_usage.this.id
}

output "items" {
  description = "returns a list of object"
  value       = oci_metering_computation_usage.this.items
}

output "query_type" {
  description = "returns a string"
  value       = oci_metering_computation_usage.this.query_type
}

output "this" {
  value = oci_metering_computation_usage.this
}
```

[top](#index)