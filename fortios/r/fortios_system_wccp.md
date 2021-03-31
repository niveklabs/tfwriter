# fortios_system_wccp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/fortios/r/fortios_system_wccp"

  # assignment_bucket_format - (optional) is a type of string
  assignment_bucket_format = null
  # assignment_dstaddr_mask - (optional) is a type of string
  assignment_dstaddr_mask = null
  # assignment_method - (optional) is a type of string
  assignment_method = null
  # assignment_srcaddr_mask - (optional) is a type of string
  assignment_srcaddr_mask = null
  # assignment_weight - (optional) is a type of number
  assignment_weight = null
  # authentication - (optional) is a type of string
  authentication = null
  # cache_engine_method - (optional) is a type of string
  cache_engine_method = null
  # cache_id - (optional) is a type of string
  cache_id = null
  # forward_method - (optional) is a type of string
  forward_method = null
  # group_address - (optional) is a type of string
  group_address = null
  # password - (optional) is a type of string
  password = null
  # ports - (optional) is a type of string
  ports = null
  # ports_defined - (optional) is a type of string
  ports_defined = null
  # primary_hash - (optional) is a type of string
  primary_hash = null
  # priority - (optional) is a type of number
  priority = null
  # protocol - (optional) is a type of number
  protocol = null
  # return_method - (optional) is a type of string
  return_method = null
  # router_id - (optional) is a type of string
  router_id = null
  # router_list - (optional) is a type of string
  router_list = null
  # server_list - (optional) is a type of string
  server_list = null
  # server_type - (optional) is a type of string
  server_type = null
  # service_id - (optional) is a type of string
  service_id = null
  # service_type - (optional) is a type of string
  service_type = null
}
```

[top](#index)

### Variables

```terraform
variable "assignment_bucket_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment_dstaddr_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment_srcaddr_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment_weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_engine_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ports" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ports_defined" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_hash" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "return_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_wccp" "this" {
  assignment_bucket_format = var.assignment_bucket_format
  assignment_dstaddr_mask  = var.assignment_dstaddr_mask
  assignment_method        = var.assignment_method
  assignment_srcaddr_mask  = var.assignment_srcaddr_mask
  assignment_weight        = var.assignment_weight
  authentication           = var.authentication
  cache_engine_method      = var.cache_engine_method
  cache_id                 = var.cache_id
  forward_method           = var.forward_method
  group_address            = var.group_address
  password                 = var.password
  ports                    = var.ports
  ports_defined            = var.ports_defined
  primary_hash             = var.primary_hash
  priority                 = var.priority
  protocol                 = var.protocol
  return_method            = var.return_method
  router_id                = var.router_id
  router_list              = var.router_list
  server_list              = var.server_list
  server_type              = var.server_type
  service_id               = var.service_id
  service_type             = var.service_type
}
```

[top](#index)

### Outputs

```terraform
output "assignment_bucket_format" {
  description = "returns a string"
  value       = fortios_system_wccp.this.assignment_bucket_format
}

output "assignment_dstaddr_mask" {
  description = "returns a string"
  value       = fortios_system_wccp.this.assignment_dstaddr_mask
}

output "assignment_method" {
  description = "returns a string"
  value       = fortios_system_wccp.this.assignment_method
}

output "assignment_srcaddr_mask" {
  description = "returns a string"
  value       = fortios_system_wccp.this.assignment_srcaddr_mask
}

output "assignment_weight" {
  description = "returns a number"
  value       = fortios_system_wccp.this.assignment_weight
}

output "authentication" {
  description = "returns a string"
  value       = fortios_system_wccp.this.authentication
}

output "cache_engine_method" {
  description = "returns a string"
  value       = fortios_system_wccp.this.cache_engine_method
}

output "cache_id" {
  description = "returns a string"
  value       = fortios_system_wccp.this.cache_id
}

output "forward_method" {
  description = "returns a string"
  value       = fortios_system_wccp.this.forward_method
}

output "group_address" {
  description = "returns a string"
  value       = fortios_system_wccp.this.group_address
}

output "id" {
  description = "returns a string"
  value       = fortios_system_wccp.this.id
}

output "ports" {
  description = "returns a string"
  value       = fortios_system_wccp.this.ports
}

output "ports_defined" {
  description = "returns a string"
  value       = fortios_system_wccp.this.ports_defined
}

output "primary_hash" {
  description = "returns a string"
  value       = fortios_system_wccp.this.primary_hash
}

output "priority" {
  description = "returns a number"
  value       = fortios_system_wccp.this.priority
}

output "protocol" {
  description = "returns a number"
  value       = fortios_system_wccp.this.protocol
}

output "return_method" {
  description = "returns a string"
  value       = fortios_system_wccp.this.return_method
}

output "router_id" {
  description = "returns a string"
  value       = fortios_system_wccp.this.router_id
}

output "router_list" {
  description = "returns a string"
  value       = fortios_system_wccp.this.router_list
}

output "server_list" {
  description = "returns a string"
  value       = fortios_system_wccp.this.server_list
}

output "server_type" {
  description = "returns a string"
  value       = fortios_system_wccp.this.server_type
}

output "service_id" {
  description = "returns a string"
  value       = fortios_system_wccp.this.service_id
}

output "service_type" {
  description = "returns a string"
  value       = fortios_system_wccp.this.service_type
}

output "this" {
  value = fortios_system_wccp.this
}
```

[top](#index)