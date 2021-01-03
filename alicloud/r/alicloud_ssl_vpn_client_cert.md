# alicloud_ssl_vpn_client_cert

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ssl_vpn_client_cert" {
  source = "./modules/alicloud/r/alicloud_ssl_vpn_client_cert"

  # name - (optional) is a type of string
  name = null
  # ssl_vpn_server_id - (required) is a type of string
  ssl_vpn_server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_vpn_server_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ssl_vpn_client_cert" "this" {
  name              = var.name
  ssl_vpn_server_id = var.ssl_vpn_server_id
}
```

[top](#index)

### Outputs

```terraform
output "ca_cert" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.ca_cert
  sensitive   = true
}

output "client_cert" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.client_cert
  sensitive   = true
}

output "client_config" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.client_config
  sensitive   = true
}

output "client_key" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.client_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ssl_vpn_client_cert.this.status
}

output "this" {
  value = alicloud_ssl_vpn_client_cert.this
}
```

[top](#index)