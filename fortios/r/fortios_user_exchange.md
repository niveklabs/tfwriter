# fortios_user_exchange

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
module "fortios_user_exchange" {
  source = "./modules/fortios/r/fortios_user_exchange"

  # auth_level - (optional) is a type of string
  auth_level = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # auto_discover_kdc - (optional) is a type of string
  auto_discover_kdc = null
  # connect_protocol - (optional) is a type of string
  connect_protocol = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # http_auth_type - (optional) is a type of string
  http_auth_type = null
  # ip - (optional) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # server_name - (optional) is a type of string
  server_name = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # username - (optional) is a type of string
  username = null

  kdc_ip = [{
    ipv4 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_discover_kdc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connect_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kdc_ip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ipv4 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_exchange" "this" {
  auth_level            = var.auth_level
  auth_type             = var.auth_type
  auto_discover_kdc     = var.auto_discover_kdc
  connect_protocol      = var.connect_protocol
  domain_name           = var.domain_name
  dynamic_sort_subtable = var.dynamic_sort_subtable
  http_auth_type        = var.http_auth_type
  ip                    = var.ip
  name                  = var.name
  password              = var.password
  server_name           = var.server_name
  ssl_min_proto_version = var.ssl_min_proto_version
  username              = var.username

  dynamic "kdc_ip" {
    for_each = var.kdc_ip
    content {
      ipv4 = kdc_ip.value["ipv4"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_level" {
  description = "returns a string"
  value       = fortios_user_exchange.this.auth_level
}

output "auth_type" {
  description = "returns a string"
  value       = fortios_user_exchange.this.auth_type
}

output "auto_discover_kdc" {
  description = "returns a string"
  value       = fortios_user_exchange.this.auto_discover_kdc
}

output "connect_protocol" {
  description = "returns a string"
  value       = fortios_user_exchange.this.connect_protocol
}

output "domain_name" {
  description = "returns a string"
  value       = fortios_user_exchange.this.domain_name
}

output "http_auth_type" {
  description = "returns a string"
  value       = fortios_user_exchange.this.http_auth_type
}

output "id" {
  description = "returns a string"
  value       = fortios_user_exchange.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_user_exchange.this.ip
}

output "name" {
  description = "returns a string"
  value       = fortios_user_exchange.this.name
}

output "server_name" {
  description = "returns a string"
  value       = fortios_user_exchange.this.server_name
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_user_exchange.this.ssl_min_proto_version
}

output "username" {
  description = "returns a string"
  value       = fortios_user_exchange.this.username
}

output "this" {
  value = fortios_user_exchange.this
}
```

[top](#index)