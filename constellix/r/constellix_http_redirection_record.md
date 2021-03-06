# constellix_http_redirection_record

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_http_redirection_record" {
  source = null

  # description - (optional) is a type of string
  description = null
  # domain_id - (required) is a type of string
  domain_id = null
  # gtd_region - (optional) is a type of number
  gtd_region = null
  # hardlink_flag - (optional) is a type of bool
  hardlink_flag = null
  # keywords - (optional) is a type of string
  keywords = null
  # name - (optional) is a type of string
  name = null
  # noanswer - (optional) is a type of bool
  noanswer = null
  # note - (optional) is a type of string
  note = null
  # parent - (optional) is a type of string
  parent = null
  # parentid - (optional) is a type of number
  parentid = null
  # redirect_type_id - (required) is a type of number
  redirect_type_id = null
  # source - (optional) is a type of string
  # source_type - (required) is a type of string
  source_type = null
  # title - (optional) is a type of string
  title = null
  # ttl - (required) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_id" {
  description = "(required)"
  type        = string
}

variable "gtd_region" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hardlink_flag" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "keywords" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "noanswer" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parentid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redirect_type_id" {
  description = "(required)"
  type        = number
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_type" {
  description = "(required)"
  type        = string
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "constellix_http_redirection_record" "this" {
  # description - (optional) is a type of string
  description = var.description
  # domain_id - (required) is a type of string
  domain_id = var.domain_id
  # gtd_region - (optional) is a type of number
  gtd_region = var.gtd_region
  # hardlink_flag - (optional) is a type of bool
  hardlink_flag = var.hardlink_flag
  # keywords - (optional) is a type of string
  keywords = var.keywords
  # name - (optional) is a type of string
  name = var.name
  # noanswer - (optional) is a type of bool
  noanswer = var.noanswer
  # note - (optional) is a type of string
  note = var.note
  # parent - (optional) is a type of string
  parent = var.parent
  # parentid - (optional) is a type of number
  parentid = var.parentid
  # redirect_type_id - (required) is a type of number
  redirect_type_id = var.redirect_type_id
  # source - (optional) is a type of string
  source = var.source
  # source_type - (required) is a type of string
  source_type = var.source_type
  # title - (optional) is a type of string
  title = var.title
  # ttl - (required) is a type of number
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type
  # url - (required) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.description
}

output "gtd_region" {
  description = "returns a number"
  value       = constellix_http_redirection_record.this.gtd_region
}

output "hardlink_flag" {
  description = "returns a bool"
  value       = constellix_http_redirection_record.this.hardlink_flag
}

output "id" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.id
}

output "keywords" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.keywords
}

output "noanswer" {
  description = "returns a bool"
  value       = constellix_http_redirection_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.note
}

output "parent" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.parent
}

output "parentid" {
  description = "returns a number"
  value       = constellix_http_redirection_record.this.parentid
}

output "source" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.source
}

output "title" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.title
}

output "type" {
  description = "returns a string"
  value       = constellix_http_redirection_record.this.type
}

output "this" {
  value = constellix_http_redirection_record.this
}
```

[top](#index)