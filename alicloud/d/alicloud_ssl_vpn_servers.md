# alicloud_ssl_vpn_servers

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
module "alicloud_ssl_vpn_servers" {
  source = "./modules/alicloud/d/alicloud_ssl_vpn_servers"

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
data "alicloud_ssl_vpn_servers" "this" {
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  vpn_gateway_id = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ssl_vpn_servers.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ssl_vpn_servers.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ssl_vpn_servers.this.names
}

output "servers" {
  description = "returns a list of object"
  value       = data.alicloud_ssl_vpn_servers.this.servers
}

output "this" {
  value = alicloud_ssl_vpn_servers.this
}
```

[top](#index)