# bigip_sys_snmp_traps

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_snmp_traps" {
  source = "./modules/bigip/r/bigip_sys_snmp_traps"

  # auth_passwordencrypted - (optional) is a type of string
  auth_passwordencrypted = null
  # auth_protocol - (optional) is a type of string
  auth_protocol = null
  # community - (optional) is a type of string
  community = null
  # description - (optional) is a type of string
  description = null
  # engine_id - (optional) is a type of string
  engine_id = null
  # host - (optional) is a type of string
  host = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # privacy_password - (optional) is a type of string
  privacy_password = null
  # privacy_password_encrypted - (optional) is a type of string
  privacy_password_encrypted = null
  # privacy_protocol - (optional) is a type of string
  privacy_protocol = null
  # security_level - (optional) is a type of string
  security_level = null
  # security_name - (optional) is a type of string
  security_name = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_passwordencrypted" {
  description = "(optional) - Encrypted password "
  type        = string
  default     = null
}

variable "auth_protocol" {
  description = "(optional) - Specifies the protocol used to authenticate the user."
  type        = string
  default     = null
}

variable "community" {
  description = "(optional) - Specifies the community string used for this trap. "
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - User defined description."
  type        = string
  default     = null
}

variable "engine_id" {
  description = "(optional) - Specifies the authoritative security engine for SNMPv3."
  type        = string
  default     = null
}

variable "host" {
  description = "(optional) - The host the trap will be sent to."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional) - The port that the trap will be sent to."
  type        = number
  default     = null
}

variable "privacy_password" {
  description = "(optional) - Specifies the clear text password used to encrypt traffic. This field will not be displayed. "
  type        = string
  default     = null
}

variable "privacy_password_encrypted" {
  description = "(optional) - Specifies the encrypted password used to encrypt traffic. "
  type        = string
  default     = null
}

variable "privacy_protocol" {
  description = "(optional) - Specifies the protocol used to encrypt traffic. "
  type        = string
  default     = null
}

variable "security_level" {
  description = "(optional) - Specifies whether or not traffic is encrypted and whether or not authentication is required."
  type        = string
  default     = null
}

variable "security_name" {
  description = "(optional) - Security name used in conjunction with SNMPv3."
  type        = string
  default     = null
}

variable "version" {
  description = "(optional) - SNMP version used for sending the trap. "
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_snmp_traps" "this" {
  auth_passwordencrypted     = var.auth_passwordencrypted
  auth_protocol              = var.auth_protocol
  community                  = var.community
  description                = var.description
  engine_id                  = var.engine_id
  host                       = var.host
  name                       = var.name
  port                       = var.port
  privacy_password           = var.privacy_password
  privacy_password_encrypted = var.privacy_password_encrypted
  privacy_protocol           = var.privacy_protocol
  security_level             = var.security_level
  security_name              = var.security_name
  version                    = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_snmp_traps.this.id
}

output "this" {
  value = bigip_sys_snmp_traps.this
}
```

[top](#index)