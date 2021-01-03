# ovh_iploadbalancing_tcp_farm_server

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_tcp_farm_server" {
  source = "./modules/ovh/r/ovh_iploadbalancing_tcp_farm_server"

  # address - (required) is a type of string
  address = null
  # backup - (optional) is a type of bool
  backup = null
  # chain - (optional) is a type of string
  chain = null
  # display_name - (optional) is a type of string
  display_name = null
  # farm_id - (required) is a type of number
  farm_id = null
  # port - (optional) is a type of number
  port = null
  # probe - (optional) is a type of bool
  probe = null
  # proxy_protocol_version - (optional) is a type of string
  proxy_protocol_version = null
  # service_name - (required) is a type of string
  service_name = null
  # ssl - (optional) is a type of bool
  ssl = null
  # status - (required) is a type of string
  status = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "backup" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "farm_id" {
  description = "(required)"
  type        = number
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "probe" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "proxy_protocol_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_tcp_farm_server" "this" {
  address                = var.address
  backup                 = var.backup
  chain                  = var.chain
  display_name           = var.display_name
  farm_id                = var.farm_id
  port                   = var.port
  probe                  = var.probe
  proxy_protocol_version = var.proxy_protocol_version
  service_name           = var.service_name
  ssl                    = var.ssl
  status                 = var.status
  weight                 = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_tcp_farm_server.this.id
}

output "this" {
  value = ovh_iploadbalancing_tcp_farm_server.this
}
```

[top](#index)