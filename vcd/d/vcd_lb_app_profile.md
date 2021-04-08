# vcd_lb_app_profile

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_lb_app_profile" {
  source = "./modules/vcd/d/vcd_lb_app_profile"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the LB Application Profile is located"
  type        = string
}

variable "name" {
  description = "(required) - LB Application Profile name for lookup"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_lb_app_profile" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "cookie_mode" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.cookie_mode
}

output "cookie_name" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.cookie_name
}

output "enable_pool_side_ssl" {
  description = "returns a bool"
  value       = data.vcd_lb_app_profile.this.enable_pool_side_ssl
}

output "enable_ssl_passthrough" {
  description = "returns a bool"
  value       = data.vcd_lb_app_profile.this.enable_ssl_passthrough
}

output "expiration" {
  description = "returns a number"
  value       = data.vcd_lb_app_profile.this.expiration
}

output "http_redirect_url" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.http_redirect_url
}

output "id" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.id
}

output "insert_x_forwarded_http_header" {
  description = "returns a bool"
  value       = data.vcd_lb_app_profile.this.insert_x_forwarded_http_header
}

output "persistence_mechanism" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.persistence_mechanism
}

output "type" {
  description = "returns a string"
  value       = data.vcd_lb_app_profile.this.type
}

output "this" {
  value = vcd_lb_app_profile.this
}
```

[top](#index)