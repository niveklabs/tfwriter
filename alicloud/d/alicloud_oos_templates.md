# alicloud_oos_templates

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_oos_templates" {
  source = "./modules/alicloud/d/alicloud_oos_templates"

  # category - (optional) is a type of string
  category = null
  # created_by - (optional) is a type of string
  created_by = null
  # created_date - (optional) is a type of string
  created_date = null
  # created_date_after - (optional) is a type of string
  created_date_after = null
  # has_trigger - (optional) is a type of bool
  has_trigger = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # share_type - (optional) is a type of string
  share_type = null
  # sort_field - (optional) is a type of string
  sort_field = null
  # sort_order - (optional) is a type of string
  sort_order = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_format - (optional) is a type of string
  template_format = null
  # template_type - (optional) is a type of string
  template_type = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_date_after" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "has_trigger" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "share_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_field" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_oos_templates" "this" {
  category           = var.category
  created_by         = var.created_by
  created_date       = var.created_date
  created_date_after = var.created_date_after
  has_trigger        = var.has_trigger
  ids                = var.ids
  name_regex         = var.name_regex
  output_file        = var.output_file
  share_type         = var.share_type
  sort_field         = var.sort_field
  sort_order         = var.sort_order
  tags               = var.tags
  template_format    = var.template_format
  template_type      = var.template_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_oos_templates.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_oos_templates.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_oos_templates.this.names
}

output "templates" {
  description = "returns a list of object"
  value       = data.alicloud_oos_templates.this.templates
}

output "this" {
  value = alicloud_oos_templates.this
}
```

[top](#index)