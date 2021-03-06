# oci_health_checks_ping_monitor

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
module "oci_health_checks_ping_monitor" {
  source = "./modules/oci/r/oci_health_checks_ping_monitor"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # interval_in_seconds - (required) is a type of number
  interval_in_seconds = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # port - (optional) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # targets - (required) is a type of list of string
  targets = []
  # timeout_in_seconds - (optional) is a type of number
  timeout_in_seconds = null
  # vantage_point_names - (optional) is a type of list of string
  vantage_point_names = []

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

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

variable "interval_in_seconds" {
  description = "(required)"
  type        = number
}

variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "targets" {
  description = "(required)"
  type        = list(string)
}

variable "timeout_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vantage_point_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
resource "oci_health_checks_ping_monitor" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # interval_in_seconds - (required) is a type of number
  interval_in_seconds = var.interval_in_seconds
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # port - (optional) is a type of number
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # targets - (required) is a type of list of string
  targets = var.targets
  # timeout_in_seconds - (optional) is a type of number
  timeout_in_seconds = var.timeout_in_seconds
  # vantage_point_names - (optional) is a type of list of string
  vantage_point_names = var.vantage_point_names

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_health_checks_ping_monitor.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_health_checks_ping_monitor.this.freeform_tags
}

output "home_region" {
  description = "returns a string"
  value       = oci_health_checks_ping_monitor.this.home_region
}

output "id" {
  description = "returns a string"
  value       = oci_health_checks_ping_monitor.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = oci_health_checks_ping_monitor.this.is_enabled
}

output "port" {
  description = "returns a number"
  value       = oci_health_checks_ping_monitor.this.port
}

output "results_url" {
  description = "returns a string"
  value       = oci_health_checks_ping_monitor.this.results_url
}

output "time_created" {
  description = "returns a string"
  value       = oci_health_checks_ping_monitor.this.time_created
}

output "timeout_in_seconds" {
  description = "returns a number"
  value       = oci_health_checks_ping_monitor.this.timeout_in_seconds
}

output "vantage_point_names" {
  description = "returns a list of string"
  value       = oci_health_checks_ping_monitor.this.vantage_point_names
}

output "this" {
  value = oci_health_checks_ping_monitor.this
}
```

[top](#index)