# fortios_user_fssopolling

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
module "fortios_user_fssopolling" {
  source = "./modules/fortios/r/fortios_user_fssopolling"

  # default_domain - (optional) is a type of string
  default_domain = null
  # fosid - (optional) is a type of number
  fosid = null
  # ldap_server - (required) is a type of string
  ldap_server = null
  # logon_history - (optional) is a type of number
  logon_history = null
  # password - (optional) is a type of string
  password = null
  # polling_frequency - (optional) is a type of number
  polling_frequency = null
  # port - (optional) is a type of number
  port = null
  # server - (required) is a type of string
  server = null
  # smb_ntlmv1_auth - (optional) is a type of string
  smb_ntlmv1_auth = null
  # smbv1 - (optional) is a type of string
  smbv1 = null
  # status - (optional) is a type of string
  status = null
  # user - (required) is a type of string
  user = null

  adgrp = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ldap_server" {
  description = "(required)"
  type        = string
}

variable "logon_history" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "polling_frequency" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "smb_ntlmv1_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smbv1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(required)"
  type        = string
}

variable "adgrp" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_fssopolling" "this" {
  default_domain    = var.default_domain
  fosid             = var.fosid
  ldap_server       = var.ldap_server
  logon_history     = var.logon_history
  password          = var.password
  polling_frequency = var.polling_frequency
  port              = var.port
  server            = var.server
  smb_ntlmv1_auth   = var.smb_ntlmv1_auth
  smbv1             = var.smbv1
  status            = var.status
  user              = var.user

  dynamic "adgrp" {
    for_each = var.adgrp
    content {
      name = adgrp.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_domain" {
  description = "returns a string"
  value       = fortios_user_fssopolling.this.default_domain
}

output "fosid" {
  description = "returns a number"
  value       = fortios_user_fssopolling.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_user_fssopolling.this.id
}

output "logon_history" {
  description = "returns a number"
  value       = fortios_user_fssopolling.this.logon_history
}

output "polling_frequency" {
  description = "returns a number"
  value       = fortios_user_fssopolling.this.polling_frequency
}

output "port" {
  description = "returns a number"
  value       = fortios_user_fssopolling.this.port
}

output "smb_ntlmv1_auth" {
  description = "returns a string"
  value       = fortios_user_fssopolling.this.smb_ntlmv1_auth
}

output "smbv1" {
  description = "returns a string"
  value       = fortios_user_fssopolling.this.smbv1
}

output "status" {
  description = "returns a string"
  value       = fortios_user_fssopolling.this.status
}

output "this" {
  value = fortios_user_fssopolling.this
}
```

[top](#index)