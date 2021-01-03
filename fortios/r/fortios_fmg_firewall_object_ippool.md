# fortios_fmg_firewall_object_ippool

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_fmg_firewall_object_ippool" {
  source = "./modules/fortios/r/fortios_fmg_firewall_object_ippool"

  # adom - (optional) is a type of string
  adom = null
  # arp_intf - (optional) is a type of string
  arp_intf = null
  # arp_reply - (optional) is a type of string
  arp_reply = null
  # associated_intf - (optional) is a type of string
  associated_intf = null
  # comment - (optional) is a type of string
  comment = null
  # endip - (required) is a type of string
  endip = null
  # name - (required) is a type of string
  name = null
  # startip - (required) is a type of string
  startip = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_intf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arp_reply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "associated_intf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
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
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_firewall_object_ippool" "this" {
  adom            = var.adom
  arp_intf        = var.arp_intf
  arp_reply       = var.arp_reply
  associated_intf = var.associated_intf
  comment         = var.comment
  endip           = var.endip
  name            = var.name
  startip         = var.startip
  type            = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_object_ippool.this.id
}

output "this" {
  value = fortios_fmg_firewall_object_ippool.this
}
```

[top](#index)