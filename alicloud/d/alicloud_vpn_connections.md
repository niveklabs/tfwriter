# alicloud_vpn_connections

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_vpn_connections" {
  source = "./modules/alicloud/d/alicloud_vpn_connections"

  # customer_gateway_id - (optional) is a type of string
  customer_gateway_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "customer_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_vpn_connections" "this" {
  # customer_gateway_id - (optional) is a type of string
  customer_gateway_id = var.customer_gateway_id
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "connections" {
  description = "returns a list of object"
  value       = data.alicloud_vpn_connections.this.connections
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_vpn_connections.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_vpn_connections.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_vpn_connections.this.names
}

output "this" {
  value = alicloud_vpn_connections.this
}
```

[top](#index)