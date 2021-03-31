# fortios_webproxy_debugurl

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
module "fortios_webproxy_debugurl" {
  source = "./modules/fortios/r/fortios_webproxy_debugurl"

  # exact - (optional) is a type of string
  exact = null
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
variable "exact" {
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
resource "fortios_webproxy_debugurl" "this" {
  exact       = var.exact
  name        = var.name
  status      = var.status
  url_pattern = var.url_pattern
}
```

[top](#index)

### Outputs

```terraform
output "exact" {
  description = "returns a string"
  value       = fortios_webproxy_debugurl.this.exact
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_debugurl.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_webproxy_debugurl.this.name
}

output "status" {
  description = "returns a string"
  value       = fortios_webproxy_debugurl.this.status
}

output "this" {
  value = fortios_webproxy_debugurl.this
}
```

[top](#index)