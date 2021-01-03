# fortios_firewallssh_setting

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
module "fortios_firewallssh_setting" {
  source = "./modules/fortios/r/fortios_firewallssh_setting"

  # caname - (optional) is a type of string
  caname = null
  # host_trusted_checking - (optional) is a type of string
  host_trusted_checking = null
  # hostkey_dsa1024 - (optional) is a type of string
  hostkey_dsa1024 = null
  # hostkey_ecdsa256 - (optional) is a type of string
  hostkey_ecdsa256 = null
  # hostkey_ecdsa384 - (optional) is a type of string
  hostkey_ecdsa384 = null
  # hostkey_ecdsa521 - (optional) is a type of string
  hostkey_ecdsa521 = null
  # hostkey_ed25519 - (optional) is a type of string
  hostkey_ed25519 = null
  # hostkey_rsa2048 - (optional) is a type of string
  hostkey_rsa2048 = null
  # untrusted_caname - (optional) is a type of string
  untrusted_caname = null
}
```

[top](#index)

### Variables

```terraform
variable "caname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_trusted_checking" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_dsa1024" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_ecdsa256" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_ecdsa384" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_ecdsa521" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_ed25519" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostkey_rsa2048" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "untrusted_caname" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallssh_setting" "this" {
  caname                = var.caname
  host_trusted_checking = var.host_trusted_checking
  hostkey_dsa1024       = var.hostkey_dsa1024
  hostkey_ecdsa256      = var.hostkey_ecdsa256
  hostkey_ecdsa384      = var.hostkey_ecdsa384
  hostkey_ecdsa521      = var.hostkey_ecdsa521
  hostkey_ed25519       = var.hostkey_ed25519
  hostkey_rsa2048       = var.hostkey_rsa2048
  untrusted_caname      = var.untrusted_caname
}
```

[top](#index)

### Outputs

```terraform
output "caname" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.caname
}

output "host_trusted_checking" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.host_trusted_checking
}

output "hostkey_dsa1024" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_dsa1024
}

output "hostkey_ecdsa256" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_ecdsa256
}

output "hostkey_ecdsa384" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_ecdsa384
}

output "hostkey_ecdsa521" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_ecdsa521
}

output "hostkey_ed25519" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_ed25519
}

output "hostkey_rsa2048" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.hostkey_rsa2048
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.id
}

output "untrusted_caname" {
  description = "returns a string"
  value       = fortios_firewallssh_setting.this.untrusted_caname
}

output "this" {
  value = fortios_firewallssh_setting.this
}
```

[top](#index)