# alicloud_ssl_vpn_server

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ssl_vpn_server" {
  source = "./modules/alicloud/r/alicloud_ssl_vpn_server"

  # cipher - (optional) is a type of string
  cipher = null
  # client_ip_pool - (required) is a type of string
  client_ip_pool = null
  # compress - (optional) is a type of bool
  compress = null
  # local_subnet - (required) is a type of string
  local_subnet = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cipher" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_ip_pool" {
  description = "(required)"
  type        = string
}

variable "compress" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_subnet" {
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

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ssl_vpn_server" "this" {
  # cipher - (optional) is a type of string
  cipher = var.cipher
  # client_ip_pool - (required) is a type of string
  client_ip_pool = var.client_ip_pool
  # compress - (optional) is a type of bool
  compress = var.compress
  # local_subnet - (required) is a type of string
  local_subnet = var.local_subnet
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "connections" {
  description = "returns a number"
  value       = alicloud_ssl_vpn_server.this.connections
}

output "id" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_server.this.id
}

output "internet_ip" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_server.this.internet_ip
}

output "max_connections" {
  description = "returns a number"
  value       = alicloud_ssl_vpn_server.this.max_connections
}

output "this" {
  value = alicloud_ssl_vpn_server.this
}
```

[top](#index)