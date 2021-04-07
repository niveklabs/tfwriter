# avi_healthmonitor

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_healthmonitor" {
  source = "./modules/avi/d/avi_healthmonitor"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_healthmonitor" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "allow_duplicate_monitors" {
  description = "returns a bool"
  value       = data.avi_healthmonitor.this.allow_duplicate_monitors
}

output "description" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.description
}

output "disable_quickstart" {
  description = "returns a bool"
  value       = data.avi_healthmonitor.this.disable_quickstart
}

output "dns_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.dns_monitor
}

output "external_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.external_monitor
}

output "failed_checks" {
  description = "returns a number"
  value       = data.avi_healthmonitor.this.failed_checks
}

output "http_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.http_monitor
}

output "https_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.https_monitor
}

output "id" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.id
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_healthmonitor.this.is_federated
}

output "monitor_port" {
  description = "returns a number"
  value       = data.avi_healthmonitor.this.monitor_port
}

output "name" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.name
}

output "radius_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.radius_monitor
}

output "receive_timeout" {
  description = "returns a number"
  value       = data.avi_healthmonitor.this.receive_timeout
}

output "send_interval" {
  description = "returns a number"
  value       = data.avi_healthmonitor.this.send_interval
}

output "sip_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.sip_monitor
}

output "successful_checks" {
  description = "returns a number"
  value       = data.avi_healthmonitor.this.successful_checks
}

output "tcp_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.tcp_monitor
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.type
}

output "udp_monitor" {
  description = "returns a set of object"
  value       = data.avi_healthmonitor.this.udp_monitor
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_healthmonitor.this.uuid
}

output "this" {
  value = avi_healthmonitor.this
}
```

[top](#index)