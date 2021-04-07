# fortios_credentialstore_domaincontroller

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
module "fortios_credentialstore_domaincontroller" {
  source = "./modules/fortios/r/fortios_credentialstore_domaincontroller"

  # domain_name - (optional) is a type of string
  domain_name = null
  # hostname - (optional) is a type of string
  hostname = null
  # ip - (optional) is a type of string
  ip = null
  # ip6 - (optional) is a type of string
  ip6 = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # server_name - (optional) is a type of string
  server_name = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_credentialstore_domaincontroller" "this" {
  # domain_name - (optional) is a type of string
  domain_name = var.domain_name
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # ip - (optional) is a type of string
  ip = var.ip
  # ip6 - (optional) is a type of string
  ip6 = var.ip6
  # password - (optional) is a type of string
  password = var.password
  # port - (optional) is a type of number
  port = var.port
  # server_name - (optional) is a type of string
  server_name = var.server_name
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "domain_name" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.domain_name
}

output "hostname" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.ip
}

output "ip6" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.ip6
}

output "port" {
  description = "returns a number"
  value       = fortios_credentialstore_domaincontroller.this.port
}

output "server_name" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.server_name
}

output "username" {
  description = "returns a string"
  value       = fortios_credentialstore_domaincontroller.this.username
}

output "this" {
  value = fortios_credentialstore_domaincontroller.this
}
```

[top](#index)