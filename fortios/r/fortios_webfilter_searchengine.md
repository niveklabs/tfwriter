# fortios_webfilter_searchengine

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
module "fortios_webfilter_searchengine" {
  source = "./modules/fortios/r/fortios_webfilter_searchengine"

  # charset - (optional) is a type of string
  charset = null
  # hostname - (optional) is a type of string
  hostname = null
  # name - (required) is a type of string
  name = null
  # query - (optional) is a type of string
  query = null
  # safesearch - (optional) is a type of string
  safesearch = null
  # safesearch_str - (optional) is a type of string
  safesearch_str = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "charset" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "safesearch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "safesearch_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_searchengine" "this" {
  # charset - (optional) is a type of string
  charset = var.charset
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # name - (required) is a type of string
  name = var.name
  # query - (optional) is a type of string
  query = var.query
  # safesearch - (optional) is a type of string
  safesearch = var.safesearch
  # safesearch_str - (optional) is a type of string
  safesearch_str = var.safesearch_str
  # url - (optional) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "charset" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.charset
}

output "hostname" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.id
}

output "query" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.query
}

output "safesearch" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.safesearch
}

output "safesearch_str" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.safesearch_str
}

output "url" {
  description = "returns a string"
  value       = fortios_webfilter_searchengine.this.url
}

output "this" {
  value = fortios_webfilter_searchengine.this
}
```

[top](#index)