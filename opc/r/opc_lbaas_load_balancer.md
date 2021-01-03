# opc_lbaas_load_balancer

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_lbaas_load_balancer" {
  source = "./modules/opc/r/opc_lbaas_load_balancer"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ip_network - (optional) is a type of string
  ip_network = null
  # name - (required) is a type of string
  name = null
  # parent_load_balancer - (optional) is a type of string
  parent_load_balancer = null
  # permitted_clients - (optional) is a type of set of string
  permitted_clients = []
  # permitted_methods - (optional) is a type of set of string
  permitted_methods = []
  # policies - (optional) is a type of set of string
  policies = []
  # region - (required) is a type of string
  region = null
  # scheme - (required) is a type of string
  scheme = null
  # server_pool - (optional) is a type of string
  server_pool = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_load_balancer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permitted_clients" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "permitted_methods" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "scheme" {
  description = "(required)"
  type        = string
}

variable "server_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_lbaas_load_balancer" "this" {
  description          = var.description
  enabled              = var.enabled
  ip_network           = var.ip_network
  name                 = var.name
  parent_load_balancer = var.parent_load_balancer
  permitted_clients    = var.permitted_clients
  permitted_methods    = var.permitted_methods
  policies             = var.policies
  region               = var.region
  scheme               = var.scheme
  server_pool          = var.server_pool
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "balancer_vips" {
  description = "returns a list of string"
  value       = opc_lbaas_load_balancer.this.balancer_vips
}

output "canonical_host_name" {
  description = "returns a string"
  value       = opc_lbaas_load_balancer.this.canonical_host_name
}

output "cloudgate_capable" {
  description = "returns a bool"
  value       = opc_lbaas_load_balancer.this.cloudgate_capable
}

output "id" {
  description = "returns a string"
  value       = opc_lbaas_load_balancer.this.id
}

output "ip_network" {
  description = "returns a string"
  value       = opc_lbaas_load_balancer.this.ip_network
}

output "uri" {
  description = "returns a string"
  value       = opc_lbaas_load_balancer.this.uri
}

output "this" {
  value = opc_lbaas_load_balancer.this
}
```

[top](#index)