# fortios_report_theme

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
module "fortios_report_theme" {
  source = "./modules/fortios/r/fortios_report_theme"

  # bullet_list_style - (optional) is a type of string
  bullet_list_style = null
  # column_count - (optional) is a type of string
  column_count = null
  # default_html_style - (optional) is a type of string
  default_html_style = null
  # default_pdf_style - (optional) is a type of string
  default_pdf_style = null
  # graph_chart_style - (optional) is a type of string
  graph_chart_style = null
  # heading1_style - (optional) is a type of string
  heading1_style = null
  # heading2_style - (optional) is a type of string
  heading2_style = null
  # heading3_style - (optional) is a type of string
  heading3_style = null
  # heading4_style - (optional) is a type of string
  heading4_style = null
  # hline_style - (optional) is a type of string
  hline_style = null
  # image_style - (optional) is a type of string
  image_style = null
  # name - (optional) is a type of string
  name = null
  # normal_text_style - (optional) is a type of string
  normal_text_style = null
  # numbered_list_style - (optional) is a type of string
  numbered_list_style = null
  # page_footer_style - (optional) is a type of string
  page_footer_style = null
  # page_header_style - (optional) is a type of string
  page_header_style = null
  # page_orient - (optional) is a type of string
  page_orient = null
  # page_style - (optional) is a type of string
  page_style = null
  # report_subtitle_style - (optional) is a type of string
  report_subtitle_style = null
  # report_title_style - (optional) is a type of string
  report_title_style = null
  # table_chart_caption_style - (optional) is a type of string
  table_chart_caption_style = null
  # table_chart_even_row_style - (optional) is a type of string
  table_chart_even_row_style = null
  # table_chart_head_style - (optional) is a type of string
  table_chart_head_style = null
  # table_chart_odd_row_style - (optional) is a type of string
  table_chart_odd_row_style = null
  # table_chart_style - (optional) is a type of string
  table_chart_style = null
  # toc_heading1_style - (optional) is a type of string
  toc_heading1_style = null
  # toc_heading2_style - (optional) is a type of string
  toc_heading2_style = null
  # toc_heading3_style - (optional) is a type of string
  toc_heading3_style = null
  # toc_heading4_style - (optional) is a type of string
  toc_heading4_style = null
  # toc_title_style - (optional) is a type of string
  toc_title_style = null
}
```

[top](#index)

### Variables

```terraform
variable "bullet_list_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "column_count" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_html_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_pdf_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graph_chart_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heading1_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heading2_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heading3_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heading4_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hline_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "normal_text_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "numbered_list_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "page_footer_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "page_header_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "page_orient" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "page_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "report_subtitle_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "report_title_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_chart_caption_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_chart_even_row_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_chart_head_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_chart_odd_row_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_chart_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "toc_heading1_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "toc_heading2_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "toc_heading3_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "toc_heading4_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "toc_title_style" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_theme" "this" {
  bullet_list_style          = var.bullet_list_style
  column_count               = var.column_count
  default_html_style         = var.default_html_style
  default_pdf_style          = var.default_pdf_style
  graph_chart_style          = var.graph_chart_style
  heading1_style             = var.heading1_style
  heading2_style             = var.heading2_style
  heading3_style             = var.heading3_style
  heading4_style             = var.heading4_style
  hline_style                = var.hline_style
  image_style                = var.image_style
  name                       = var.name
  normal_text_style          = var.normal_text_style
  numbered_list_style        = var.numbered_list_style
  page_footer_style          = var.page_footer_style
  page_header_style          = var.page_header_style
  page_orient                = var.page_orient
  page_style                 = var.page_style
  report_subtitle_style      = var.report_subtitle_style
  report_title_style         = var.report_title_style
  table_chart_caption_style  = var.table_chart_caption_style
  table_chart_even_row_style = var.table_chart_even_row_style
  table_chart_head_style     = var.table_chart_head_style
  table_chart_odd_row_style  = var.table_chart_odd_row_style
  table_chart_style          = var.table_chart_style
  toc_heading1_style         = var.toc_heading1_style
  toc_heading2_style         = var.toc_heading2_style
  toc_heading3_style         = var.toc_heading3_style
  toc_heading4_style         = var.toc_heading4_style
  toc_title_style            = var.toc_title_style
}
```

[top](#index)

### Outputs

```terraform
output "bullet_list_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.bullet_list_style
}

output "column_count" {
  description = "returns a string"
  value       = fortios_report_theme.this.column_count
}

output "default_html_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.default_html_style
}

output "default_pdf_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.default_pdf_style
}

output "graph_chart_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.graph_chart_style
}

output "heading1_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.heading1_style
}

output "heading2_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.heading2_style
}

output "heading3_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.heading3_style
}

output "heading4_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.heading4_style
}

output "hline_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.hline_style
}

output "id" {
  description = "returns a string"
  value       = fortios_report_theme.this.id
}

output "image_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.image_style
}

output "name" {
  description = "returns a string"
  value       = fortios_report_theme.this.name
}

output "normal_text_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.normal_text_style
}

output "numbered_list_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.numbered_list_style
}

output "page_footer_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.page_footer_style
}

output "page_header_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.page_header_style
}

output "page_orient" {
  description = "returns a string"
  value       = fortios_report_theme.this.page_orient
}

output "page_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.page_style
}

output "report_subtitle_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.report_subtitle_style
}

output "report_title_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.report_title_style
}

output "table_chart_caption_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.table_chart_caption_style
}

output "table_chart_even_row_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.table_chart_even_row_style
}

output "table_chart_head_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.table_chart_head_style
}

output "table_chart_odd_row_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.table_chart_odd_row_style
}

output "table_chart_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.table_chart_style
}

output "toc_heading1_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.toc_heading1_style
}

output "toc_heading2_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.toc_heading2_style
}

output "toc_heading3_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.toc_heading3_style
}

output "toc_heading4_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.toc_heading4_style
}

output "toc_title_style" {
  description = "returns a string"
  value       = fortios_report_theme.this.toc_title_style
}

output "this" {
  value = fortios_report_theme.this
}
```

[top](#index)