# vultr_bare_metal_server

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_bare_metal_server" {
  source = "./modules/vultr/r/vultr_bare_metal_server"

  # activation_email - (optional) is a type of bool
  activation_email = null
  # app_id - (optional) is a type of number
  app_id = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # hostname - (optional) is a type of string
  hostname = null
  # label - (optional) is a type of string
  label = null
  # os_id - (optional) is a type of number
  os_id = null
  # plan - (required) is a type of string
  plan = null
  # region - (required) is a type of string
  region = null
  # reserved_ipv4 - (optional) is a type of string
  reserved_ipv4 = null
  # script_id - (optional) is a type of string
  script_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # ssh_key_ids - (optional) is a type of list of string
  ssh_key_ids = []
  # tag - (optional) is a type of string
  tag = null
  # user_data - (optional) is a type of string
  user_data = null
}
```

[top](#index)

### Variables

```terraform
variable "activation_email" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "app_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "plan" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "reserved_ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_key_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_bare_metal_server" "this" {
  # activation_email - (optional) is a type of bool
  activation_email = var.activation_email
  # app_id - (optional) is a type of number
  app_id = var.app_id
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = var.enable_ipv6
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # label - (optional) is a type of string
  label = var.label
  # os_id - (optional) is a type of number
  os_id = var.os_id
  # plan - (required) is a type of string
  plan = var.plan
  # region - (required) is a type of string
  region = var.region
  # reserved_ipv4 - (optional) is a type of string
  reserved_ipv4 = var.reserved_ipv4
  # script_id - (optional) is a type of string
  script_id = var.script_id
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # ssh_key_ids - (optional) is a type of list of string
  ssh_key_ids = var.ssh_key_ids
  # tag - (optional) is a type of string
  tag = var.tag
  # user_data - (optional) is a type of string
  user_data = var.user_data
}
```

[top](#index)

### Outputs

```terraform
output "app_id" {
  description = "returns a number"
  value       = vultr_bare_metal_server.this.app_id
}

output "cpu_count" {
  description = "returns a number"
  value       = vultr_bare_metal_server.this.cpu_count
}

output "date_created" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.date_created
}

output "default_password" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.default_password
  sensitive   = true
}

output "disk" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.disk
}

output "gateway_v4" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.gateway_v4
}

output "id" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.id
}

output "main_ip" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.main_ip
}

output "netmask_v4" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.netmask_v4
}

output "os" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.os
}

output "os_id" {
  description = "returns a number"
  value       = vultr_bare_metal_server.this.os_id
}

output "ram" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.ram
}

output "reserved_ipv4" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.reserved_ipv4
}

output "status" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.status
}

output "user_data" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.user_data
}

output "v6_main_ip" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.v6_main_ip
}

output "v6_network" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.v6_network
}

output "v6_network_size" {
  description = "returns a string"
  value       = vultr_bare_metal_server.this.v6_network_size
}

output "this" {
  value = vultr_bare_metal_server.this
}
```

[top](#index)