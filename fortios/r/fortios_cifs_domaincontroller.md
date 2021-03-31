# fortios_cifs_domaincontroller

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
module "fortios_cifs_domaincontroller" {
  source = "./modules/fortios/r/fortios_cifs_domaincontroller"

  # domain_name - (optional) is a type of string
  domain_name = null
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
resource "fortios_cifs_domaincontroller" "this" {
  domain_name = var.domain_name
  ip          = var.ip
  ip6         = var.ip6
  password    = var.password
  port        = var.port
  server_name = var.server_name
  username    = var.username
}
```

[top](#index)

### Outputs

```terraform
output "domain_name" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.domain_name
}

output "id" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.ip
}

output "ip6" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.ip6
}

output "port" {
  description = "returns a number"
  value       = fortios_cifs_domaincontroller.this.port
}

output "server_name" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.server_name
}

output "username" {
  description = "returns a string"
  value       = fortios_cifs_domaincontroller.this.username
}

output "this" {
  value = fortios_cifs_domaincontroller.this
}
```

[top](#index)