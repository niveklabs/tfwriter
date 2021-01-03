# fortios_vpn_l2tp

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
module "fortios_vpn_l2tp" {
  source = "./modules/fortios/r/fortios_vpn_l2tp"

  # eip - (optional) is a type of string
  eip = null
  # enforce_ipsec - (optional) is a type of string
  enforce_ipsec = null
  # sip - (optional) is a type of string
  sip = null
  # status - (required) is a type of string
  status = null
  # usrgrp - (optional) is a type of string
  usrgrp = null
}
```

[top](#index)

### Variables

```terraform
variable "eip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enforce_ipsec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "usrgrp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpn_l2tp" "this" {
  eip           = var.eip
  enforce_ipsec = var.enforce_ipsec
  sip           = var.sip
  status        = var.status
  usrgrp        = var.usrgrp
}
```

[top](#index)

### Outputs

```terraform
output "eip" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.eip
}

output "enforce_ipsec" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.enforce_ipsec
}

output "id" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.id
}

output "sip" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.sip
}

output "usrgrp" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.usrgrp
}

output "this" {
  value = fortios_vpn_l2tp.this
}
```

[top](#index)