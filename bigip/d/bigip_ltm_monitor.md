# bigip_ltm_monitor

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_monitor" {
  source = "./modules/bigip/d/bigip_ltm_monitor"

  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the LTM Monitor"
  type        = string
}

variable "partition" {
  description = "(required) - partition of LTM Monitor"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "bigip_ltm_monitor" "this" {
  name      = var.name
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "adaptive" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.adaptive
}

output "adaptive_limit" {
  description = "returns a number"
  value       = data.bigip_ltm_monitor.this.adaptive_limit
}

output "database" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.database
}

output "defaults_from" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.defaults_from
}

output "destination" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.destination
}

output "filename" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.filename
}

output "id" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = data.bigip_ltm_monitor.this.interval
}

output "ip_dscp" {
  description = "returns a number"
  value       = data.bigip_ltm_monitor.this.ip_dscp
}

output "manual_resume" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.manual_resume
}

output "mode" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.mode
}

output "receive_disable" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.receive_disable
}

output "reverse" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.reverse
}

output "time_until_up" {
  description = "returns a number"
  value       = data.bigip_ltm_monitor.this.time_until_up
}

output "timeout" {
  description = "returns a number"
  value       = data.bigip_ltm_monitor.this.timeout
}

output "transparent" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.transparent
}

output "username" {
  description = "returns a string"
  value       = data.bigip_ltm_monitor.this.username
}

output "this" {
  value = bigip_ltm_monitor.this
}
```

[top](#index)