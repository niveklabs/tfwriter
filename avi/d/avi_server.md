# avi_server

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
module "avi_server" {
  source = "./modules/avi/d/avi_server"

  # ip - (required) is a type of string
  ip = null
  # pool_ref - (required) is a type of string
  pool_ref = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required)"
  type        = string
}

variable "pool_ref" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "avi_server" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # pool_ref - (required) is a type of string
  pool_ref = var.pool_ref
}
```

[top](#index)

### Outputs

```terraform
output "autoscaling_group_name" {
  description = "returns a string"
  value       = data.avi_server.this.autoscaling_group_name
}

output "availability_zone" {
  description = "returns a string"
  value       = data.avi_server.this.availability_zone
}

output "description" {
  description = "returns a string"
  value       = data.avi_server.this.description
}

output "discovered_networks" {
  description = "returns a list of object"
  value       = data.avi_server.this.discovered_networks
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_server.this.enabled
}

output "external_orchestration_id" {
  description = "returns a string"
  value       = data.avi_server.this.external_orchestration_id
}

output "external_uuid" {
  description = "returns a string"
  value       = data.avi_server.this.external_uuid
}

output "hostname" {
  description = "returns a string"
  value       = data.avi_server.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.avi_server.this.id
}

output "location" {
  description = "returns a set of object"
  value       = data.avi_server.this.location
}

output "mac_address" {
  description = "returns a string"
  value       = data.avi_server.this.mac_address
}

output "nw_ref" {
  description = "returns a string"
  value       = data.avi_server.this.nw_ref
}

output "port" {
  description = "returns a number"
  value       = data.avi_server.this.port
}

output "prst_hdr_val" {
  description = "returns a string"
  value       = data.avi_server.this.prst_hdr_val
}

output "ratio" {
  description = "returns a number"
  value       = data.avi_server.this.ratio
}

output "resolve_server_by_dns" {
  description = "returns a bool"
  value       = data.avi_server.this.resolve_server_by_dns
}

output "rewrite_host_header" {
  description = "returns a bool"
  value       = data.avi_server.this.rewrite_host_header
}

output "server_node" {
  description = "returns a string"
  value       = data.avi_server.this.server_node
}

output "static" {
  description = "returns a bool"
  value       = data.avi_server.this.static
}

output "type" {
  description = "returns a string"
  value       = data.avi_server.this.type
}

output "verify_network" {
  description = "returns a bool"
  value       = data.avi_server.this.verify_network
}

output "vm_ref" {
  description = "returns a string"
  value       = data.avi_server.this.vm_ref
}

output "this" {
  value = avi_server.this
}
```

[top](#index)