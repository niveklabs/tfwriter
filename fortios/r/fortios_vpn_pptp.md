# fortios_vpn_pptp

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
module "fortios_vpn_pptp" {
  source = "./modules/fortios/r/fortios_vpn_pptp"

  # eip - (optional) is a type of string
  eip = null
  # ip_mode - (optional) is a type of string
  ip_mode = null
  # local_ip - (optional) is a type of string
  local_ip = null
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

variable "ip_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_ip" {
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
resource "fortios_vpn_pptp" "this" {
  eip      = var.eip
  ip_mode  = var.ip_mode
  local_ip = var.local_ip
  sip      = var.sip
  status   = var.status
  usrgrp   = var.usrgrp
}
```

[top](#index)

### Outputs

```terraform
output "eip" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.eip
}

output "id" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.id
}

output "ip_mode" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.ip_mode
}

output "local_ip" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.local_ip
}

output "sip" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.sip
}

output "usrgrp" {
  description = "returns a string"
  value       = fortios_vpn_pptp.this.usrgrp
}

output "this" {
  value = fortios_vpn_pptp.this
}
```

[top](#index)