# fortios_webproxy_urlmatch

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_webproxy_urlmatch" {
  source = "./modules/fortios/r/fortios_webproxy_urlmatch"

  # cache_exemption - (optional) is a type of string
  cache_exemption = null
  # comment - (optional) is a type of string
  comment = null
  # forward_server - (optional) is a type of string
  forward_server = null
  # name - (optional) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
  # url_pattern - (required) is a type of string
  url_pattern = null
}
```

[top](#index)

### Variables

```terraform
variable "cache_exemption" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forward_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_pattern" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_urlmatch" "this" {
  cache_exemption = var.cache_exemption
  comment         = var.comment
  forward_server  = var.forward_server
  name            = var.name
  status          = var.status
  url_pattern     = var.url_pattern
}
```

[top](#index)

### Outputs

```terraform
output "cache_exemption" {
  description = "returns a string"
  value       = fortios_webproxy_urlmatch.this.cache_exemption
}

output "forward_server" {
  description = "returns a string"
  value       = fortios_webproxy_urlmatch.this.forward_server
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_urlmatch.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_webproxy_urlmatch.this.name
}

output "status" {
  description = "returns a string"
  value       = fortios_webproxy_urlmatch.this.status
}

output "this" {
  value = fortios_webproxy_urlmatch.this
}
```

[top](#index)