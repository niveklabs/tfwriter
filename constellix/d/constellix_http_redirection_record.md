# constellix_http_redirection_record

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  # name - (required) is a type of string
  name = null
  # noanswer - (optional) is a type of bool
  noanswer = null
  # note - (optional) is a type of string
  note = null
  # parent - (optional) is a type of string
  parent = null
  # parentid - (optional) is a type of number
  parentid = null
  # redirect_type_id - (optional) is a type of number
  redirect_type_id = null
  # source - (optional) is a type of string
  # source_type - (required) is a type of string
  source_type = null
  # title - (optional) is a type of string
  title = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null
  # url - (optional) is a type of string
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
  description = "(required)"
  type        = string
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
  description = "(optional)"
  type        = number
  default     = null
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
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
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

### Datasource

```terraform
data "constellix_http_redirection_record" "this" {
  description      = var.description
  domain_id        = var.domain_id
  gtd_region       = var.gtd_region
  hardlink_flag    = var.hardlink_flag
  keywords         = var.keywords
  name             = var.name
  noanswer         = var.noanswer
  note             = var.note
  parent           = var.parent
  parentid         = var.parentid
  redirect_type_id = var.redirect_type_id
  source           = var.source
  source_type      = var.source_type
  title            = var.title
  ttl              = var.ttl
  type             = var.type
  url              = var.url
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.description
}

output "gtd_region" {
  description = "returns a number"
  value       = data.constellix_http_redirection_record.this.gtd_region
}

output "hardlink_flag" {
  description = "returns a bool"
  value       = data.constellix_http_redirection_record.this.hardlink_flag
}

output "id" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.id
}

output "keywords" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.keywords
}

output "noanswer" {
  description = "returns a bool"
  value       = data.constellix_http_redirection_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.note
}

output "parent" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.parent
}

output "parentid" {
  description = "returns a number"
  value       = data.constellix_http_redirection_record.this.parentid
}

output "redirect_type_id" {
  description = "returns a number"
  value       = data.constellix_http_redirection_record.this.redirect_type_id
}

output "source" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.source
}

output "title" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.title
}

output "ttl" {
  description = "returns a number"
  value       = data.constellix_http_redirection_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.type
}

output "url" {
  description = "returns a string"
  value       = data.constellix_http_redirection_record.this.url
}

output "this" {
  value = constellix_http_redirection_record.this
}
```

[top](#index)