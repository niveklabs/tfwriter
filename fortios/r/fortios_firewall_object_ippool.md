# fortios_firewall_object_ippool

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
module "fortios_firewall_object_ippool" {
  source = "./modules/fortios/r/fortios_firewall_object_ippool"

  # arp_reply - (optional) is a type of string
  arp_reply = null
  # comments - (optional) is a type of string
  comments = null
  # endip - (required) is a type of string
  endip = null
  # name - (required) is a type of string
  name = null
  # startip - (required) is a type of string
  startip = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "arp_reply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "endip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "startip" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_object_ippool" "this" {
  # arp_reply - (optional) is a type of string
  arp_reply = var.arp_reply
  # comments - (optional) is a type of string
  comments = var.comments
  # endip - (required) is a type of string
  endip = var.endip
  # name - (required) is a type of string
  name = var.name
  # startip - (required) is a type of string
  startip = var.startip
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arp_reply" {
  description = "returns a string"
  value       = fortios_firewall_object_ippool.this.arp_reply
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_ippool.this.id
}

output "this" {
  value = fortios_firewall_object_ippool.this
}
```

[top](#index)