# fortios_authentication_scheme

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
module "fortios_authentication_scheme" {
  source = "./modules/fortios/r/fortios_authentication_scheme"

  # domain_controller - (optional) is a type of string
  domain_controller = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fsso_agent_for_ntlm - (optional) is a type of string
  fsso_agent_for_ntlm = null
  # fsso_guest - (optional) is a type of string
  fsso_guest = null
  # kerberos_keytab - (optional) is a type of string
  kerberos_keytab = null
  # method - (required) is a type of string
  method = null
  # name - (optional) is a type of string
  name = null
  # negotiate_ntlm - (optional) is a type of string
  negotiate_ntlm = null
  # require_tfa - (optional) is a type of string
  require_tfa = null
  # ssh_ca - (optional) is a type of string
  ssh_ca = null

  user_database = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_controller" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso_agent_for_ntlm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso_guest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kerberos_keytab" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "method" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "negotiate_ntlm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "require_tfa" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_ca" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_database" {
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
resource "fortios_authentication_scheme" "this" {
  # domain_controller - (optional) is a type of string
  domain_controller = var.domain_controller
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fsso_agent_for_ntlm - (optional) is a type of string
  fsso_agent_for_ntlm = var.fsso_agent_for_ntlm
  # fsso_guest - (optional) is a type of string
  fsso_guest = var.fsso_guest
  # kerberos_keytab - (optional) is a type of string
  kerberos_keytab = var.kerberos_keytab
  # method - (required) is a type of string
  method = var.method
  # name - (optional) is a type of string
  name = var.name
  # negotiate_ntlm - (optional) is a type of string
  negotiate_ntlm = var.negotiate_ntlm
  # require_tfa - (optional) is a type of string
  require_tfa = var.require_tfa
  # ssh_ca - (optional) is a type of string
  ssh_ca = var.ssh_ca

  dynamic "user_database" {
    for_each = var.user_database
    content {
      # name - (optional) is a type of string
      name = user_database.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "domain_controller" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.domain_controller
}

output "fsso_agent_for_ntlm" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.fsso_agent_for_ntlm
}

output "fsso_guest" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.fsso_guest
}

output "id" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.id
}

output "kerberos_keytab" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.kerberos_keytab
}

output "name" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.name
}

output "negotiate_ntlm" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.negotiate_ntlm
}

output "require_tfa" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.require_tfa
}

output "ssh_ca" {
  description = "returns a string"
  value       = fortios_authentication_scheme.this.ssh_ca
}

output "this" {
  value = fortios_authentication_scheme.this
}
```

[top](#index)