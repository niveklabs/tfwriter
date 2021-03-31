# fortios_fmg_firewall_object_address

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
module "fortios_fmg_firewall_object_address" {
  source = "./modules/fortios/r/fortios_fmg_firewall_object_address"

  # adom - (optional) is a type of string
  adom = null
  # allow_routing - (optional) is a type of string
  allow_routing = null
  # associated_intf - (optional) is a type of string
  associated_intf = null
  # comment - (optional) is a type of string
  comment = null
  # end_ip - (optional) is a type of string
  end_ip = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # name - (required) is a type of string
  name = null
  # start_ip - (optional) is a type of string
  start_ip = null
  # subnet - (optional) is a type of string
  subnet = null
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

variable "allow_routing" {
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

variable "end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet" {
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
resource "fortios_fmg_firewall_object_address" "this" {
  adom            = var.adom
  allow_routing   = var.allow_routing
  associated_intf = var.associated_intf
  comment         = var.comment
  end_ip          = var.end_ip
  fqdn            = var.fqdn
  name            = var.name
  start_ip        = var.start_ip
  subnet          = var.subnet
  type            = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_object_address.this.id
}

output "this" {
  value = fortios_fmg_firewall_object_address.this
}
```

[top](#index)