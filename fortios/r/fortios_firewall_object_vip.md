# fortios_firewall_object_vip

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
module "fortios_firewall_object_vip" {
  source = "./modules/fortios/r/fortios_firewall_object_vip"

  # comment - (optional) is a type of string
  comment = null
  # extintf - (optional) is a type of string
  extintf = null
  # extip - (required) is a type of string
  extip = null
  # extport - (optional) is a type of string
  extport = null
  # mappedip - (required) is a type of list of string
  mappedip = []
  # mappedport - (optional) is a type of string
  mappedport = null
  # name - (required) is a type of string
  name = null
  # portforward - (optional) is a type of string
  portforward = null
  # protocol - (optional) is a type of string
  protocol = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extintf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extip" {
  description = "(required)"
  type        = string
}

variable "extport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mappedip" {
  description = "(required)"
  type        = list(string)
}

variable "mappedport" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "portforward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_object_vip" "this" {
  comment     = var.comment
  extintf     = var.extintf
  extip       = var.extip
  extport     = var.extport
  mappedip    = var.mappedip
  mappedport  = var.mappedport
  name        = var.name
  portforward = var.portforward
  protocol    = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "extintf" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.extintf
}

output "extport" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.extport
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.id
}

output "mappedport" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.mappedport
}

output "portforward" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.portforward
}

output "protocol" {
  description = "returns a string"
  value       = fortios_firewall_object_vip.this.protocol
}

output "this" {
  value = fortios_firewall_object_vip.this
}
```

[top](#index)