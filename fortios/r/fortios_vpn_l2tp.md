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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_vpn_l2tp" {
  source = "./modules/fortios/r/fortios_vpn_l2tp"

  # compress - (optional) is a type of string
  compress = null
  # eip - (optional) is a type of string
  eip = null
  # enforce_ipsec - (optional) is a type of string
  enforce_ipsec = null
  # lcp_echo_interval - (optional) is a type of number
  lcp_echo_interval = null
  # lcp_max_echo_fails - (optional) is a type of number
  lcp_max_echo_fails = null
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
variable "compress" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "lcp_echo_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lcp_max_echo_fails" {
  description = "(optional)"
  type        = number
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
  # compress - (optional) is a type of string
  compress = var.compress
  # eip - (optional) is a type of string
  eip = var.eip
  # enforce_ipsec - (optional) is a type of string
  enforce_ipsec = var.enforce_ipsec
  # lcp_echo_interval - (optional) is a type of number
  lcp_echo_interval = var.lcp_echo_interval
  # lcp_max_echo_fails - (optional) is a type of number
  lcp_max_echo_fails = var.lcp_max_echo_fails
  # sip - (optional) is a type of string
  sip = var.sip
  # status - (required) is a type of string
  status = var.status
  # usrgrp - (optional) is a type of string
  usrgrp = var.usrgrp
}
```

[top](#index)

### Outputs

```terraform
output "compress" {
  description = "returns a string"
  value       = fortios_vpn_l2tp.this.compress
}

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

output "lcp_echo_interval" {
  description = "returns a number"
  value       = fortios_vpn_l2tp.this.lcp_echo_interval
}

output "lcp_max_echo_fails" {
  description = "returns a number"
  value       = fortios_vpn_l2tp.this.lcp_max_echo_fails
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