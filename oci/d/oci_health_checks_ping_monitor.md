# oci_health_checks_ping_monitor

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/oci/d/oci_health_checks_ping_monitor"

  # monitor_id - (required) is a type of string
  monitor_id = null
}
```

[top](#index)

### Variables

```terraform
variable "monitor_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_health_checks_ping_monitor" "this" {
  monitor_id = var.monitor_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_health_checks_ping_monitor.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_health_checks_ping_monitor.this.freeform_tags
}

output "home_region" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.home_region
}

output "id" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.id
}

output "interval_in_seconds" {
  description = "returns a number"
  value       = data.oci_health_checks_ping_monitor.this.interval_in_seconds
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_health_checks_ping_monitor.this.is_enabled
}

output "port" {
  description = "returns a number"
  value       = data.oci_health_checks_ping_monitor.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.protocol
}

output "results_url" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.results_url
}

output "targets" {
  description = "returns a list of string"
  value       = data.oci_health_checks_ping_monitor.this.targets
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_monitor.this.time_created
}

output "timeout_in_seconds" {
  description = "returns a number"
  value       = data.oci_health_checks_ping_monitor.this.timeout_in_seconds
}

output "vantage_point_names" {
  description = "returns a list of string"
  value       = data.oci_health_checks_ping_monitor.this.vantage_point_names
}

output "this" {
  value = oci_health_checks_ping_monitor.this
}
```

[top](#index)