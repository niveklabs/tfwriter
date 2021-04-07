# fortios_wanopt_authgroup

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
module "fortios_wanopt_authgroup" {
  source = "./modules/fortios/r/fortios_wanopt_authgroup"

  # auth_method - (optional) is a type of string
  auth_method = null
  # cert - (required) is a type of string
  cert = null
  # name - (optional) is a type of string
  name = null
  # peer - (optional) is a type of string
  peer = null
  # peer_accept - (optional) is a type of string
  peer_accept = null
  # psk - (optional) is a type of string
  psk = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_accept" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "psk" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_authgroup" "this" {
  # auth_method - (optional) is a type of string
  auth_method = var.auth_method
  # cert - (required) is a type of string
  cert = var.cert
  # name - (optional) is a type of string
  name = var.name
  # peer - (optional) is a type of string
  peer = var.peer
  # peer_accept - (optional) is a type of string
  peer_accept = var.peer_accept
  # psk - (optional) is a type of string
  psk = var.psk
}
```

[top](#index)

### Outputs

```terraform
output "auth_method" {
  description = "returns a string"
  value       = fortios_wanopt_authgroup.this.auth_method
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_authgroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wanopt_authgroup.this.name
}

output "peer" {
  description = "returns a string"
  value       = fortios_wanopt_authgroup.this.peer
}

output "peer_accept" {
  description = "returns a string"
  value       = fortios_wanopt_authgroup.this.peer_accept
}

output "this" {
  value = fortios_wanopt_authgroup.this
}
```

[top](#index)