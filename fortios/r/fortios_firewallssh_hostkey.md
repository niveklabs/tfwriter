# fortios_firewallssh_hostkey

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
module "fortios_firewallssh_hostkey" {
  source = "./modules/fortios/r/fortios_firewallssh_hostkey"

  # hostname - (optional) is a type of string
  hostname = null
  # ip - (optional) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # nid - (optional) is a type of string
  nid = null
  # port - (optional) is a type of number
  port = null
  # public_key - (optional) is a type of string
  public_key = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallssh_hostkey" "this" {
  hostname   = var.hostname
  ip         = var.ip
  name       = var.name
  nid        = var.nid
  port       = var.port
  public_key = var.public_key
  status     = var.status
  type       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "hostname" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.ip
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.name
}

output "nid" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.nid
}

output "port" {
  description = "returns a number"
  value       = fortios_firewallssh_hostkey.this.port
}

output "status" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.status
}

output "type" {
  description = "returns a string"
  value       = fortios_firewallssh_hostkey.this.type
}

output "this" {
  value = fortios_firewallssh_hostkey.this
}
```

[top](#index)