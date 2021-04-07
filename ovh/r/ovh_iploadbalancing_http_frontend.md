# ovh_iploadbalancing_http_frontend

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
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_http_frontend" {
  source = "./modules/ovh/r/ovh_iploadbalancing_http_frontend"

  # allowed_source - (optional) is a type of list of string
  allowed_source = []
  # dedicated_ipfo - (optional) is a type of list of string
  dedicated_ipfo = []
  # default_farm_id - (optional) is a type of number
  default_farm_id = null
  # default_ssl_id - (optional) is a type of number
  default_ssl_id = null
  # disabled - (optional) is a type of bool
  disabled = null
  # display_name - (optional) is a type of string
  display_name = null
  # port - (required) is a type of string
  port = null
  # redirect_location - (optional) is a type of string
  redirect_location = null
  # service_name - (required) is a type of string
  service_name = null
  # ssl - (optional) is a type of bool
  ssl = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_source" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dedicated_ipfo" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "default_farm_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_ssl_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(required)"
  type        = string
}

variable "redirect_location" {
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

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_http_frontend" "this" {
  # allowed_source - (optional) is a type of list of string
  allowed_source = var.allowed_source
  # dedicated_ipfo - (optional) is a type of list of string
  dedicated_ipfo = var.dedicated_ipfo
  # default_farm_id - (optional) is a type of number
  default_farm_id = var.default_farm_id
  # default_ssl_id - (optional) is a type of number
  default_ssl_id = var.default_ssl_id
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # port - (required) is a type of string
  port = var.port
  # redirect_location - (optional) is a type of string
  redirect_location = var.redirect_location
  # service_name - (required) is a type of string
  service_name = var.service_name
  # ssl - (optional) is a type of bool
  ssl = var.ssl
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "default_farm_id" {
  description = "returns a number"
  value       = ovh_iploadbalancing_http_frontend.this.default_farm_id
}

output "default_ssl_id" {
  description = "returns a number"
  value       = ovh_iploadbalancing_http_frontend.this.default_ssl_id
}

output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_http_frontend.this.id
}

output "this" {
  value = ovh_iploadbalancing_http_frontend.this
}
```

[top](#index)