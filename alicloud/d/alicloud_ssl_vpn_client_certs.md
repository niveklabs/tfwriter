# alicloud_ssl_vpn_client_certs

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ssl_vpn_client_certs" {
  source = "./modules/alicloud/d/alicloud_ssl_vpn_client_certs"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # ssl_vpn_server_id - (optional) is a type of string
  ssl_vpn_server_id = null
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

variable "ssl_vpn_server_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ssl_vpn_client_certs" "this" {
  ids               = var.ids
  name_regex        = var.name_regex
  output_file       = var.output_file
  ssl_vpn_server_id = var.ssl_vpn_server_id
}
```

[top](#index)

### Outputs

```terraform
output "certs" {
  description = "returns a list of object"
  value       = data.alicloud_ssl_vpn_client_certs.this.certs
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ssl_vpn_client_certs.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ssl_vpn_client_certs.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ssl_vpn_client_certs.this.names
}

output "this" {
  value = alicloud_ssl_vpn_client_certs.this
}
```

[top](#index)