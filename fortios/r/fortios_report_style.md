# fortios_report_style

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
module "fortios_report_style" {
  source = "./modules/fortios/r/fortios_report_style"

  # align - (optional) is a type of string
  align = null
  # bg_color - (optional) is a type of string
  bg_color = null
  # border_bottom - (optional) is a type of string
  border_bottom = null
  # border_left - (optional) is a type of string
  border_left = null
  # border_right - (optional) is a type of string
  border_right = null
  # border_top - (optional) is a type of string
  border_top = null
  # column_gap - (optional) is a type of string
  column_gap = null
  # column_span - (optional) is a type of string
  column_span = null
  # fg_color - (optional) is a type of string
  fg_color = null
  # font_family - (optional) is a type of string
  font_family = null
  # font_size - (optional) is a type of string
  font_size = null
  # font_style - (optional) is a type of string
  font_style = null
  # font_weight - (optional) is a type of string
  font_weight = null
  # height - (optional) is a type of string
  height = null
  # line_height - (optional) is a type of string
  line_height = null
  # margin_bottom - (optional) is a type of string
  margin_bottom = null
  # margin_left - (optional) is a type of string
  margin_left = null
  # margin_right - (optional) is a type of string
  margin_right = null
  # margin_top - (optional) is a type of string
  margin_top = null
  # name - (optional) is a type of string
  name = null
  # options - (optional) is a type of string
  options = null
  # padding_bottom - (optional) is a type of string
  padding_bottom = null
  # padding_left - (optional) is a type of string
  padding_left = null
  # padding_right - (optional) is a type of string
  padding_right = null
  # padding_top - (optional) is a type of string
  padding_top = null
  # width - (optional) is a type of string
  width = null
}
```

[top](#index)

### Variables

```terraform
variable "align" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bg_color" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "border_bottom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "border_left" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "border_right" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "border_top" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "column_gap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "column_span" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fg_color" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "font_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "font_size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "font_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "font_weight" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "height" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "line_height" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "margin_bottom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "margin_left" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "margin_right" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "margin_top" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "padding_bottom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "padding_left" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "padding_right" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "padding_top" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "width" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_style" "this" {
  # align - (optional) is a type of string
  align = var.align
  # bg_color - (optional) is a type of string
  bg_color = var.bg_color
  # border_bottom - (optional) is a type of string
  border_bottom = var.border_bottom
  # border_left - (optional) is a type of string
  border_left = var.border_left
  # border_right - (optional) is a type of string
  border_right = var.border_right
  # border_top - (optional) is a type of string
  border_top = var.border_top
  # column_gap - (optional) is a type of string
  column_gap = var.column_gap
  # column_span - (optional) is a type of string
  column_span = var.column_span
  # fg_color - (optional) is a type of string
  fg_color = var.fg_color
  # font_family - (optional) is a type of string
  font_family = var.font_family
  # font_size - (optional) is a type of string
  font_size = var.font_size
  # font_style - (optional) is a type of string
  font_style = var.font_style
  # font_weight - (optional) is a type of string
  font_weight = var.font_weight
  # height - (optional) is a type of string
  height = var.height
  # line_height - (optional) is a type of string
  line_height = var.line_height
  # margin_bottom - (optional) is a type of string
  margin_bottom = var.margin_bottom
  # margin_left - (optional) is a type of string
  margin_left = var.margin_left
  # margin_right - (optional) is a type of string
  margin_right = var.margin_right
  # margin_top - (optional) is a type of string
  margin_top = var.margin_top
  # name - (optional) is a type of string
  name = var.name
  # options - (optional) is a type of string
  options = var.options
  # padding_bottom - (optional) is a type of string
  padding_bottom = var.padding_bottom
  # padding_left - (optional) is a type of string
  padding_left = var.padding_left
  # padding_right - (optional) is a type of string
  padding_right = var.padding_right
  # padding_top - (optional) is a type of string
  padding_top = var.padding_top
  # width - (optional) is a type of string
  width = var.width
}
```

[top](#index)

### Outputs

```terraform
output "align" {
  description = "returns a string"
  value       = fortios_report_style.this.align
}

output "bg_color" {
  description = "returns a string"
  value       = fortios_report_style.this.bg_color
}

output "border_bottom" {
  description = "returns a string"
  value       = fortios_report_style.this.border_bottom
}

output "border_left" {
  description = "returns a string"
  value       = fortios_report_style.this.border_left
}

output "border_right" {
  description = "returns a string"
  value       = fortios_report_style.this.border_right
}

output "border_top" {
  description = "returns a string"
  value       = fortios_report_style.this.border_top
}

output "column_gap" {
  description = "returns a string"
  value       = fortios_report_style.this.column_gap
}

output "column_span" {
  description = "returns a string"
  value       = fortios_report_style.this.column_span
}

output "fg_color" {
  description = "returns a string"
  value       = fortios_report_style.this.fg_color
}

output "font_family" {
  description = "returns a string"
  value       = fortios_report_style.this.font_family
}

output "font_size" {
  description = "returns a string"
  value       = fortios_report_style.this.font_size
}

output "font_style" {
  description = "returns a string"
  value       = fortios_report_style.this.font_style
}

output "font_weight" {
  description = "returns a string"
  value       = fortios_report_style.this.font_weight
}

output "height" {
  description = "returns a string"
  value       = fortios_report_style.this.height
}

output "id" {
  description = "returns a string"
  value       = fortios_report_style.this.id
}

output "line_height" {
  description = "returns a string"
  value       = fortios_report_style.this.line_height
}

output "margin_bottom" {
  description = "returns a string"
  value       = fortios_report_style.this.margin_bottom
}

output "margin_left" {
  description = "returns a string"
  value       = fortios_report_style.this.margin_left
}

output "margin_right" {
  description = "returns a string"
  value       = fortios_report_style.this.margin_right
}

output "margin_top" {
  description = "returns a string"
  value       = fortios_report_style.this.margin_top
}

output "name" {
  description = "returns a string"
  value       = fortios_report_style.this.name
}

output "options" {
  description = "returns a string"
  value       = fortios_report_style.this.options
}

output "padding_bottom" {
  description = "returns a string"
  value       = fortios_report_style.this.padding_bottom
}

output "padding_left" {
  description = "returns a string"
  value       = fortios_report_style.this.padding_left
}

output "padding_right" {
  description = "returns a string"
  value       = fortios_report_style.this.padding_right
}

output "padding_top" {
  description = "returns a string"
  value       = fortios_report_style.this.padding_top
}

output "width" {
  description = "returns a string"
  value       = fortios_report_style.this.width
}

output "this" {
  value = fortios_report_style.this
}
```

[top](#index)