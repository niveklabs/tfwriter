# vcd_lb_service_monitor

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_lb_service_monitor" {
  source = "./modules/vcd/d/vcd_lb_service_monitor"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Service Monitor is located"
  type        = string
}

variable "name" {
  description = "(required) - LB Service Monitor name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_lb_service_monitor" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "expected" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.expected
}

output "extension" {
  description = "returns a map of string"
  value       = data.vcd_lb_service_monitor.this.extension
}

output "id" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.id
}

output "interval" {
  description = "returns a number"
  value       = data.vcd_lb_service_monitor.this.interval
}

output "max_retries" {
  description = "returns a number"
  value       = data.vcd_lb_service_monitor.this.max_retries
}

output "method" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.method
}

output "receive" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.receive
}

output "send" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.send
}

output "timeout" {
  description = "returns a number"
  value       = data.vcd_lb_service_monitor.this.timeout
}

output "type" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.type
}

output "url" {
  description = "returns a string"
  value       = data.vcd_lb_service_monitor.this.url
}

output "this" {
  value = vcd_lb_service_monitor.this
}
```

[top](#index)