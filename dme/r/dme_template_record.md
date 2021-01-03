# dme_template_record

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_template_record" {
  source = "./modules/dme/r/dme_template_record"

  # caa_type - (optional) is a type of string
  caa_type = null
  # description - (optional) is a type of string
  description = null
  # dynamic_dns - (optional) is a type of string
  dynamic_dns = null
  # gtd_location - (optional) is a type of string
  gtd_location = null
  # hardlink - (optional) is a type of string
  hardlink = null
  # issuer_critical - (optional) is a type of string
  issuer_critical = null
  # keywords - (optional) is a type of string
  keywords = null
  # mx_level - (optional) is a type of string
  mx_level = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # port - (optional) is a type of string
  port = null
  # priority - (optional) is a type of string
  priority = null
  # redirect_type - (optional) is a type of string
  redirect_type = null
  # template_id - (required) is a type of string
  template_id = null
  # title - (optional) is a type of string
  title = null
  # ttl - (required) is a type of string
  ttl = null
  # type - (required) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
  # weight - (optional) is a type of string
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "caa_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtd_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hardlink" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "issuer_critical" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keywords" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mx_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redirect_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_id" {
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
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "dme_template_record" "this" {
  caa_type        = var.caa_type
  description     = var.description
  dynamic_dns     = var.dynamic_dns
  gtd_location    = var.gtd_location
  hardlink        = var.hardlink
  issuer_critical = var.issuer_critical
  keywords        = var.keywords
  mx_level        = var.mx_level
  name            = var.name
  password        = var.password
  port            = var.port
  priority        = var.priority
  redirect_type   = var.redirect_type
  template_id     = var.template_id
  title           = var.title
  ttl             = var.ttl
  type            = var.type
  value           = var.value
  weight          = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "caa_type" {
  description = "returns a string"
  value       = dme_template_record.this.caa_type
}

output "description" {
  description = "returns a string"
  value       = dme_template_record.this.description
}

output "dynamic_dns" {
  description = "returns a string"
  value       = dme_template_record.this.dynamic_dns
}

output "gtd_location" {
  description = "returns a string"
  value       = dme_template_record.this.gtd_location
}

output "hardlink" {
  description = "returns a string"
  value       = dme_template_record.this.hardlink
}

output "id" {
  description = "returns a string"
  value       = dme_template_record.this.id
}

output "issuer_critical" {
  description = "returns a string"
  value       = dme_template_record.this.issuer_critical
}

output "keywords" {
  description = "returns a string"
  value       = dme_template_record.this.keywords
}

output "mx_level" {
  description = "returns a string"
  value       = dme_template_record.this.mx_level
}

output "password" {
  description = "returns a string"
  value       = dme_template_record.this.password
}

output "port" {
  description = "returns a string"
  value       = dme_template_record.this.port
}

output "priority" {
  description = "returns a string"
  value       = dme_template_record.this.priority
}

output "redirect_type" {
  description = "returns a string"
  value       = dme_template_record.this.redirect_type
}

output "title" {
  description = "returns a string"
  value       = dme_template_record.this.title
}

output "weight" {
  description = "returns a string"
  value       = dme_template_record.this.weight
}

output "this" {
  value = dme_template_record.this
}
```

[top](#index)