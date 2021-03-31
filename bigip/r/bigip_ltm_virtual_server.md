# bigip_ltm_virtual_server

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "bigip_ltm_virtual_server" {
  source = null

  # client_profiles - (optional) is a type of set of string
  client_profiles = []
  # default_persistence_profile - (optional) is a type of string
  default_persistence_profile = null
  # description - (optional) is a type of string
  description = null
  # destination - (required) is a type of string
  destination = null
  # fallback_persistence_profile - (optional) is a type of string
  fallback_persistence_profile = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # irules - (optional) is a type of list of string
  irules = []
  # mask - (optional) is a type of string
  mask = null
  # name - (required) is a type of string
  name = null
  # persistence_profiles - (optional) is a type of set of string
  persistence_profiles = []
  # policies - (optional) is a type of set of string
  policies = []
  # pool - (optional) is a type of string
  pool = null
  # port - (required) is a type of number
  port = null
  # profiles - (optional) is a type of set of string
  profiles = []
  # server_profiles - (optional) is a type of set of string
  server_profiles = []
  # snatpool - (optional) is a type of string
  snatpool = null
  # source - (optional) is a type of string
  # source_address_translation - (optional) is a type of string
  source_address_translation = null
  # state - (optional) is a type of string
  state = null
  # translate_address - (optional) is a type of string
  translate_address = null
  # translate_port - (optional) is a type of string
  translate_port = null
  # vlans - (optional) is a type of set of string
  vlans = []
  # vlans_enabled - (optional) is a type of bool
  vlans_enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "client_profiles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "default_persistence_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination" {
  description = "(required)"
  type        = string
}

variable "fallback_persistence_profile" {
  description = "(optional) - Fallback persistence profile"
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - all, tcp, udp"
  type        = string
  default     = null
}

variable "irules" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "mask" {
  description = "(optional) - subnet mask"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the virtual server"
  type        = string
}

variable "persistence_profiles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "policies" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "pool" {
  description = "(optional) - Default pool for this virtual server"
  type        = string
  default     = null
}

variable "port" {
  description = "(required) - Listen port for the virtual server"
  type        = number
}

variable "profiles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "server_profiles" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "snatpool" {
  description = "(optional) - Name of the snatpool to use. Requires source_address_translation to be set to 'snat'."
  type        = string
  default     = null
}

variable "source" {
  description = "(optional) - Source IP and mask for the virtual server"
  type        = string
  default     = null
}

variable "source_address_translation" {
  description = "(optional) - none, automap, snat"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - Specifies whether the virtual server and its resources are available for load balancing. The default is Enabled"
  type        = string
  default     = null
}

variable "translate_address" {
  description = "(optional) - To enable _ disable Address translation"
  type        = string
  default     = null
}

variable "translate_port" {
  description = "(optional) - To enable _ disable port translation"
  type        = string
  default     = null
}

variable "vlans" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vlans_enabled" {
  description = "(optional) - Enables the virtual server on the VLANs specified by the VLANs option."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_virtual_server" "this" {
  client_profiles              = var.client_profiles
  default_persistence_profile  = var.default_persistence_profile
  description                  = var.description
  destination                  = var.destination
  fallback_persistence_profile = var.fallback_persistence_profile
  ip_protocol                  = var.ip_protocol
  irules                       = var.irules
  mask                         = var.mask
  name                         = var.name
  persistence_profiles         = var.persistence_profiles
  policies                     = var.policies
  pool                         = var.pool
  port                         = var.port
  profiles                     = var.profiles
  server_profiles              = var.server_profiles
  snatpool                     = var.snatpool
  source                       = var.source
  source_address_translation   = var.source_address_translation
  state                        = var.state
  translate_address            = var.translate_address
  translate_port               = var.translate_port
  vlans                        = var.vlans
  vlans_enabled                = var.vlans_enabled
}
```

[top](#index)

### Outputs

```terraform
output "client_profiles" {
  description = "returns a set of string"
  value       = bigip_ltm_virtual_server.this.client_profiles
}

output "fallback_persistence_profile" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.fallback_persistence_profile
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.id
}

output "ip_protocol" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.ip_protocol
}

output "mask" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.mask
}

output "profiles" {
  description = "returns a set of string"
  value       = bigip_ltm_virtual_server.this.profiles
}

output "server_profiles" {
  description = "returns a set of string"
  value       = bigip_ltm_virtual_server.this.server_profiles
}

output "snatpool" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.snatpool
}

output "source" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.source
}

output "source_address_translation" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.source_address_translation
}

output "translate_address" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.translate_address
}

output "translate_port" {
  description = "returns a string"
  value       = bigip_ltm_virtual_server.this.translate_port
}

output "vlans_enabled" {
  description = "returns a bool"
  value       = bigip_ltm_virtual_server.this.vlans_enabled
}

output "this" {
  value = bigip_ltm_virtual_server.this
}
```

[top](#index)