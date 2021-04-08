# vcd_lb_virtual_server

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
module "vcd_lb_virtual_server" {
  source = "./modules/vcd/d/vcd_lb_virtual_server"

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
  description = "(required) - Edge gateway name in which the Virtual Server is located"
  type        = string
}

variable "name" {
  description = "(required) - Virtual Server name for lookup"
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
data "vcd_lb_virtual_server" "this" {
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
output "app_profile_id" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.app_profile_id
}

output "app_rule_ids" {
  description = "returns a list of string"
  value       = data.vcd_lb_virtual_server.this.app_rule_ids
}

output "connection_limit" {
  description = "returns a number"
  value       = data.vcd_lb_virtual_server.this.connection_limit
}

output "connection_rate_limit" {
  description = "returns a number"
  value       = data.vcd_lb_virtual_server.this.connection_rate_limit
}

output "description" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.description
}

output "enable_acceleration" {
  description = "returns a bool"
  value       = data.vcd_lb_virtual_server.this.enable_acceleration
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_lb_virtual_server.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.ip_address
}

output "port" {
  description = "returns a number"
  value       = data.vcd_lb_virtual_server.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.protocol
}

output "server_pool_id" {
  description = "returns a string"
  value       = data.vcd_lb_virtual_server.this.server_pool_id
}

output "this" {
  value = vcd_lb_virtual_server.this
}
```

[top](#index)