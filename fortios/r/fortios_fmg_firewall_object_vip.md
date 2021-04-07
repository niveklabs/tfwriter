# fortios_fmg_firewall_object_vip

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
module "fortios_fmg_firewall_object_vip" {
  source = "./modules/fortios/r/fortios_fmg_firewall_object_vip"

  # adom - (optional) is a type of string
  adom = null
  # arp_reply - (optional) is a type of string
  arp_reply = null
  # comment - (optional) is a type of string
  comment = null
  # config_default - (optional) is a type of string
  config_default = null
  # ext_intf - (optional) is a type of string
  ext_intf = null
  # ext_ip - (optional) is a type of string
  ext_ip = null
  # mapped_addr - (optional) is a type of string
  mapped_addr = null
  # mapped_ip - (optional) is a type of string
  mapped_ip = null
  # name - (required) is a type of string
  name = null
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

variable "arp_reply" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_default" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ext_intf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ext_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mapped_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mapped_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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
resource "fortios_fmg_firewall_object_vip" "this" {
  # adom - (optional) is a type of string
  adom = var.adom
  # arp_reply - (optional) is a type of string
  arp_reply = var.arp_reply
  # comment - (optional) is a type of string
  comment = var.comment
  # config_default - (optional) is a type of string
  config_default = var.config_default
  # ext_intf - (optional) is a type of string
  ext_intf = var.ext_intf
  # ext_ip - (optional) is a type of string
  ext_ip = var.ext_ip
  # mapped_addr - (optional) is a type of string
  mapped_addr = var.mapped_addr
  # mapped_ip - (optional) is a type of string
  mapped_ip = var.mapped_ip
  # name - (required) is a type of string
  name = var.name
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_object_vip.this.id
}

output "this" {
  value = fortios_fmg_firewall_object_vip.this
}
```

[top](#index)