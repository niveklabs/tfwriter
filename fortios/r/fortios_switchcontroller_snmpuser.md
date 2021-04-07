# fortios_switchcontroller_snmpuser

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
module "fortios_switchcontroller_snmpuser" {
  source = "./modules/fortios/r/fortios_switchcontroller_snmpuser"

  # auth_proto - (optional) is a type of string
  auth_proto = null
  # auth_pwd - (optional) is a type of string
  auth_pwd = null
  # name - (optional) is a type of string
  name = null
  # priv_proto - (optional) is a type of string
  priv_proto = null
  # priv_pwd - (optional) is a type of string
  priv_pwd = null
  # queries - (optional) is a type of string
  queries = null
  # query_port - (optional) is a type of number
  query_port = null
  # security_level - (optional) is a type of string
  security_level = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priv_proto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priv_pwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "queries" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_level" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_snmpuser" "this" {
  # auth_proto - (optional) is a type of string
  auth_proto = var.auth_proto
  # auth_pwd - (optional) is a type of string
  auth_pwd = var.auth_pwd
  # name - (optional) is a type of string
  name = var.name
  # priv_proto - (optional) is a type of string
  priv_proto = var.priv_proto
  # priv_pwd - (optional) is a type of string
  priv_pwd = var.priv_pwd
  # queries - (optional) is a type of string
  queries = var.queries
  # query_port - (optional) is a type of number
  query_port = var.query_port
  # security_level - (optional) is a type of string
  security_level = var.security_level
}
```

[top](#index)

### Outputs

```terraform
output "auth_proto" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.auth_proto
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.name
}

output "priv_proto" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.priv_proto
}

output "queries" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.queries
}

output "query_port" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmpuser.this.query_port
}

output "security_level" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpuser.this.security_level
}

output "this" {
  value = fortios_switchcontroller_snmpuser.this
}
```

[top](#index)