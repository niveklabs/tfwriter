# opc_lbaas_listener

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
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_lbaas_listener" {
  source = "./modules/opc/r/opc_lbaas_listener"

  # balancer_protocol - (required) is a type of string
  balancer_protocol = null
  # certificates - (optional) is a type of set of string
  certificates = []
  # enabled - (optional) is a type of bool
  enabled = null
  # load_balancer - (required) is a type of string
  load_balancer = null
  # name - (required) is a type of string
  name = null
  # path_prefixes - (optional) is a type of set of string
  path_prefixes = []
  # policies - (optional) is a type of set of string
  policies = []
  # port - (required) is a type of number
  port = null
  # server_pool - (optional) is a type of string
  server_pool = null
  # server_protocol - (required) is a type of string
  server_protocol = null
  # tags - (optional) is a type of set of string
  tags = []
  # virtual_hosts - (optional) is a type of set of string
  virtual_hosts = []
}
```

[top](#index)

### Variables

```terraform
variable "balancer_protocol" {
  description = "(required)"
  type        = string
}

variable "certificates" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancer" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path_prefixes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "server_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_protocol" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "virtual_hosts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_lbaas_listener" "this" {
  # balancer_protocol - (required) is a type of string
  balancer_protocol = var.balancer_protocol
  # certificates - (optional) is a type of set of string
  certificates = var.certificates
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # load_balancer - (required) is a type of string
  load_balancer = var.load_balancer
  # name - (required) is a type of string
  name = var.name
  # path_prefixes - (optional) is a type of set of string
  path_prefixes = var.path_prefixes
  # policies - (optional) is a type of set of string
  policies = var.policies
  # port - (required) is a type of number
  port = var.port
  # server_pool - (optional) is a type of string
  server_pool = var.server_pool
  # server_protocol - (required) is a type of string
  server_protocol = var.server_protocol
  # tags - (optional) is a type of set of string
  tags = var.tags
  # virtual_hosts - (optional) is a type of set of string
  virtual_hosts = var.virtual_hosts
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_lbaas_listener.this.id
}

output "operation_details" {
  description = "returns a string"
  value       = opc_lbaas_listener.this.operation_details
}

output "parent_listener" {
  description = "returns a string"
  value       = opc_lbaas_listener.this.parent_listener
}

output "state" {
  description = "returns a bool"
  value       = opc_lbaas_listener.this.state
}

output "uri" {
  description = "returns a string"
  value       = opc_lbaas_listener.this.uri
}

output "this" {
  value = opc_lbaas_listener.this
}
```

[top](#index)