# fortios_user_domaincontroller

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
module "fortios_user_domaincontroller" {
  source = "./modules/fortios/r/fortios_user_domaincontroller"

  # domain_name - (optional) is a type of string
  domain_name = null
  # ip_address - (required) is a type of string
  ip_address = null
  # ldap_server - (required) is a type of string
  ldap_server = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null

  extra_server = [{
    id         = null
    ip_address = null
    port       = null
  }]
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

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "ldap_server" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extra_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id         = number
      ip_address = string
      port       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_domaincontroller" "this" {
  domain_name = var.domain_name
  ip_address  = var.ip_address
  ldap_server = var.ldap_server
  name        = var.name
  port        = var.port

  dynamic "extra_server" {
    for_each = var.extra_server
    content {
      id         = extra_server.value["id"]
      ip_address = extra_server.value["ip_address"]
      port       = extra_server.value["port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "domain_name" {
  description = "returns a string"
  value       = fortios_user_domaincontroller.this.domain_name
}

output "id" {
  description = "returns a string"
  value       = fortios_user_domaincontroller.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_user_domaincontroller.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_user_domaincontroller.this.port
}

output "this" {
  value = fortios_user_domaincontroller.this
}
```

[top](#index)