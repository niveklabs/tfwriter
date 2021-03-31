# oci_health_checks_ping_probe

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_health_checks_ping_probe" {
  source = "./modules/oci/r/oci_health_checks_ping_probe"

  # compartment_id - (required) is a type of string
  compartment_id = null
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
resource "oci_health_checks_ping_probe" "this" {
  compartment_id      = var.compartment_id
  port                = var.port
  protocol            = var.protocol
  targets             = var.targets
  timeout_in_seconds  = var.timeout_in_seconds
  vantage_point_names = var.vantage_point_names

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
output "home_region" {
  description = "returns a string"
  value       = oci_health_checks_ping_probe.this.home_region
}

output "id" {
  description = "returns a string"
  value       = oci_health_checks_ping_probe.this.id
}

output "port" {
  description = "returns a number"
  value       = oci_health_checks_ping_probe.this.port
}

output "results_url" {
  description = "returns a string"
  value       = oci_health_checks_ping_probe.this.results_url
}

output "time_created" {
  description = "returns a string"
  value       = oci_health_checks_ping_probe.this.time_created
}

output "timeout_in_seconds" {
  description = "returns a number"
  value       = oci_health_checks_ping_probe.this.timeout_in_seconds
}

output "vantage_point_names" {
  description = "returns a list of string"
  value       = oci_health_checks_ping_probe.this.vantage_point_names
}

output "this" {
  value = oci_health_checks_ping_probe.this
}
```

[top](#index)