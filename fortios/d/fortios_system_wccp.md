# fortios_system_wccp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "fortios_system_wccp" {
  source = "./modules/fortios/d/fortios_system_wccp"

  # service_id - (required) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "service_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_wccp" "this" {
  service_id = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "assignment_bucket_format" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.assignment_bucket_format
}

output "assignment_dstaddr_mask" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.assignment_dstaddr_mask
}

output "assignment_method" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.assignment_method
}

output "assignment_srcaddr_mask" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.assignment_srcaddr_mask
}

output "assignment_weight" {
  description = "returns a number"
  value       = data.fortios_system_wccp.this.assignment_weight
}

output "authentication" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.authentication
}

output "cache_engine_method" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.cache_engine_method
}

output "cache_id" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.cache_id
}

output "forward_method" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.forward_method
}

output "group_address" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.group_address
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.id
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.password
  sensitive   = true
}

output "ports" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.ports
}

output "ports_defined" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.ports_defined
}

output "primary_hash" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.primary_hash
}

output "priority" {
  description = "returns a number"
  value       = data.fortios_system_wccp.this.priority
}

output "protocol" {
  description = "returns a number"
  value       = data.fortios_system_wccp.this.protocol
}

output "return_method" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.return_method
}

output "router_id" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.router_id
}

output "router_list" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.router_list
}

output "server_list" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.server_list
}

output "server_type" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.server_type
}

output "service_type" {
  description = "returns a string"
  value       = data.fortios_system_wccp.this.service_type
}

output "this" {
  value = fortios_system_wccp.this
}
```

[top](#index)