# fortios_vpnsslweb_realm

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
module "fortios_vpnsslweb_realm" {
  source = "./modules/fortios/r/fortios_vpnsslweb_realm"

  # login_page - (optional) is a type of string
  login_page = null
  # max_concurrent_user - (optional) is a type of number
  max_concurrent_user = null
  # nas_ip - (optional) is a type of string
  nas_ip = null
  # radius_port - (optional) is a type of number
  radius_port = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # url_path - (optional) is a type of string
  url_path = null
  # virtual_host - (optional) is a type of string
  virtual_host = null
  # virtual_host_only - (optional) is a type of string
  virtual_host_only = null
}
```

[top](#index)

### Variables

```terraform
variable "login_page" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_concurrent_user" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nas_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "radius_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_host_only" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnsslweb_realm" "this" {
  # login_page - (optional) is a type of string
  login_page = var.login_page
  # max_concurrent_user - (optional) is a type of number
  max_concurrent_user = var.max_concurrent_user
  # nas_ip - (optional) is a type of string
  nas_ip = var.nas_ip
  # radius_port - (optional) is a type of number
  radius_port = var.radius_port
  # radius_server - (optional) is a type of string
  radius_server = var.radius_server
  # url_path - (optional) is a type of string
  url_path = var.url_path
  # virtual_host - (optional) is a type of string
  virtual_host = var.virtual_host
  # virtual_host_only - (optional) is a type of string
  virtual_host_only = var.virtual_host_only
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.id
}

output "max_concurrent_user" {
  description = "returns a number"
  value       = fortios_vpnsslweb_realm.this.max_concurrent_user
}

output "nas_ip" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.nas_ip
}

output "radius_port" {
  description = "returns a number"
  value       = fortios_vpnsslweb_realm.this.radius_port
}

output "radius_server" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.radius_server
}

output "url_path" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.url_path
}

output "virtual_host_only" {
  description = "returns a string"
  value       = fortios_vpnsslweb_realm.this.virtual_host_only
}

output "this" {
  value = fortios_vpnsslweb_realm.this
}
```

[top](#index)