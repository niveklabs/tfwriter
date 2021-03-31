# fortios_vpnipsec_manualkey

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
module "fortios_vpnipsec_manualkey" {
  source = "./modules/fortios/r/fortios_vpnipsec_manualkey"

  # authentication - (required) is a type of string
  authentication = null
  # authkey - (optional) is a type of string
  authkey = null
  # enckey - (optional) is a type of string
  enckey = null
  # encryption - (required) is a type of string
  encryption = null
  # interface - (required) is a type of string
  interface = null
  # local_gw - (optional) is a type of string
  local_gw = null
  # localspi - (optional) is a type of string
  localspi = null
  # name - (optional) is a type of string
  name = null
  # remote_gw - (required) is a type of string
  remote_gw = null
  # remotespi - (optional) is a type of string
  remotespi = null
}
```

[top](#index)

### Variables

```terraform
variable "authentication" {
  description = "(required)"
  type        = string
}

variable "authkey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enckey" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption" {
  description = "(required)"
  type        = string
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "local_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "localspi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_gw" {
  description = "(required)"
  type        = string
}

variable "remotespi" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnipsec_manualkey" "this" {
  authentication = var.authentication
  authkey        = var.authkey
  enckey         = var.enckey
  encryption     = var.encryption
  interface      = var.interface
  local_gw       = var.local_gw
  localspi       = var.localspi
  name           = var.name
  remote_gw      = var.remote_gw
  remotespi      = var.remotespi
}
```

[top](#index)

### Outputs

```terraform
output "authkey" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.authkey
  sensitive   = true
}

output "enckey" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.enckey
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.id
}

output "local_gw" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.local_gw
}

output "localspi" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.localspi
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.name
}

output "remotespi" {
  description = "returns a string"
  value       = fortios_vpnipsec_manualkey.this.remotespi
}

output "this" {
  value = fortios_vpnipsec_manualkey.this
}
```

[top](#index)