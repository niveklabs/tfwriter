# fortios_report_layout

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
module "fortios_report_layout" {
  source = "./modules/fortios/r/fortios_report_layout"

  # cutoff_option - (optional) is a type of string
  cutoff_option = null
  # cutoff_time - (optional) is a type of string
  cutoff_time = null
  # day - (optional) is a type of string
  day = null
  # description - (optional) is a type of string
  description = null
  # email_recipients - (optional) is a type of string
  email_recipients = null
  # email_send - (optional) is a type of string
  email_send = null
  # format - (optional) is a type of string
  format = null
  # max_pdf_report - (optional) is a type of number
  max_pdf_report = null
  # name - (optional) is a type of string
  name = null
  # options - (optional) is a type of string
  options = null
  # schedule_type - (optional) is a type of string
  schedule_type = null
  # style_theme - (required) is a type of string
  style_theme = null
  # subtitle - (optional) is a type of string
  subtitle = null
  # time - (optional) is a type of string
  time = null
  # title - (optional) is a type of string
  title = null

  body_item = [{
    chart            = null
    chart_options    = null
    column           = null
    content          = null
    description      = null
    drill_down_items = null
    drill_down_types = null
    hide             = null
    id               = null
    img_src          = null
    list = [{
      content = null
      id      = null
    }]
    list_component = null
    misc_component = null
    parameters = [{
      id    = null
      name  = null
      value = null
    }]
    style                = null
    table_caption_style  = null
    table_column_widths  = null
    table_even_row_style = null
    table_head_style     = null
    table_odd_row_style  = null
    text_component       = null
    title                = null
    top_n                = null
    type                 = null
  }]

  page = [{
    column_break_before = null
    footer = [{
      footer_item = [{
        content     = null
        description = null
        id          = null
        img_src     = null
        style       = null
        type        = null
      }]
      style = null
    }]
    header = [{
      header_item = [{
        content     = null
        description = null
        id          = null
        img_src     = null
        style       = null
        type        = null
      }]
      style = null
    }]
    options           = null
    page_break_before = null
    paper             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cutoff_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cutoff_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_recipients" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_send" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_pdf_report" {
  description = "(optional)"
  type        = number
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

variable "schedule_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "style_theme" {
  description = "(required)"
  type        = string
}

variable "subtitle" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "body_item" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      chart            = string
      chart_options    = string
      column           = number
      content          = string
      description      = string
      drill_down_items = string
      drill_down_types = string
      hide             = string
      id               = number
      img_src          = string
      list = list(object(
        {
          content = string
          id      = number
        }
      ))
      list_component = string
      misc_component = string
      parameters = list(object(
        {
          id    = number
          name  = string
          value = string
        }
      ))
      style                = string
      table_caption_style  = string
      table_column_widths  = string
      table_even_row_style = string
      table_head_style     = string
      table_odd_row_style  = string
      text_component       = string
      title                = string
      top_n                = number
      type                 = string
    }
  ))
  default = []
}

variable "page" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      column_break_before = string
      footer = list(object(
        {
          footer_item = list(object(
            {
              content     = string
              description = string
              id          = number
              img_src     = string
              style       = string
              type        = string
            }
          ))
          style = string
        }
      ))
      header = list(object(
        {
          header_item = list(object(
            {
              content     = string
              description = string
              id          = number
              img_src     = string
              style       = string
              type        = string
            }
          ))
          style = string
        }
      ))
      options           = string
      page_break_before = string
      paper             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_layout" "this" {
  cutoff_option    = var.cutoff_option
  cutoff_time      = var.cutoff_time
  day              = var.day
  description      = var.description
  email_recipients = var.email_recipients
  email_send       = var.email_send
  format           = var.format
  max_pdf_report   = var.max_pdf_report
  name             = var.name
  options          = var.options
  schedule_type    = var.schedule_type
  style_theme      = var.style_theme
  subtitle         = var.subtitle
  time             = var.time
  title            = var.title

  dynamic "body_item" {
    for_each = var.body_item
    content {
      chart                = body_item.value["chart"]
      chart_options        = body_item.value["chart_options"]
      column               = body_item.value["column"]
      content              = body_item.value["content"]
      description          = body_item.value["description"]
      drill_down_items     = body_item.value["drill_down_items"]
      drill_down_types     = body_item.value["drill_down_types"]
      hide                 = body_item.value["hide"]
      id                   = body_item.value["id"]
      img_src              = body_item.value["img_src"]
      list_component       = body_item.value["list_component"]
      misc_component       = body_item.value["misc_component"]
      style                = body_item.value["style"]
      table_caption_style  = body_item.value["table_caption_style"]
      table_column_widths  = body_item.value["table_column_widths"]
      table_even_row_style = body_item.value["table_even_row_style"]
      table_head_style     = body_item.value["table_head_style"]
      table_odd_row_style  = body_item.value["table_odd_row_style"]
      text_component       = body_item.value["text_component"]
      title                = body_item.value["title"]
      top_n                = body_item.value["top_n"]
      type                 = body_item.value["type"]

      dynamic "list" {
        for_each = body_item.value.list
        content {
          content = list.value["content"]
          id      = list.value["id"]
        }
      }

      dynamic "parameters" {
        for_each = body_item.value.parameters
        content {
          id    = parameters.value["id"]
          name  = parameters.value["name"]
          value = parameters.value["value"]
        }
      }

    }
  }

  dynamic "page" {
    for_each = var.page
    content {
      column_break_before = page.value["column_break_before"]
      options             = page.value["options"]
      page_break_before   = page.value["page_break_before"]
      paper               = page.value["paper"]

      dynamic "footer" {
        for_each = page.value.footer
        content {
          style = footer.value["style"]

          dynamic "footer_item" {
            for_each = footer.value.footer_item
            content {
              content     = footer_item.value["content"]
              description = footer_item.value["description"]
              id          = footer_item.value["id"]
              img_src     = footer_item.value["img_src"]
              style       = footer_item.value["style"]
              type        = footer_item.value["type"]
            }
          }

        }
      }

      dynamic "header" {
        for_each = page.value.header
        content {
          style = header.value["style"]

          dynamic "header_item" {
            for_each = header.value.header_item
            content {
              content     = header_item.value["content"]
              description = header_item.value["description"]
              id          = header_item.value["id"]
              img_src     = header_item.value["img_src"]
              style       = header_item.value["style"]
              type        = header_item.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cutoff_option" {
  description = "returns a string"
  value       = fortios_report_layout.this.cutoff_option
}

output "cutoff_time" {
  description = "returns a string"
  value       = fortios_report_layout.this.cutoff_time
}

output "day" {
  description = "returns a string"
  value       = fortios_report_layout.this.day
}

output "description" {
  description = "returns a string"
  value       = fortios_report_layout.this.description
}

output "email_recipients" {
  description = "returns a string"
  value       = fortios_report_layout.this.email_recipients
}

output "email_send" {
  description = "returns a string"
  value       = fortios_report_layout.this.email_send
}

output "format" {
  description = "returns a string"
  value       = fortios_report_layout.this.format
}

output "id" {
  description = "returns a string"
  value       = fortios_report_layout.this.id
}

output "max_pdf_report" {
  description = "returns a number"
  value       = fortios_report_layout.this.max_pdf_report
}

output "name" {
  description = "returns a string"
  value       = fortios_report_layout.this.name
}

output "options" {
  description = "returns a string"
  value       = fortios_report_layout.this.options
}

output "schedule_type" {
  description = "returns a string"
  value       = fortios_report_layout.this.schedule_type
}

output "subtitle" {
  description = "returns a string"
  value       = fortios_report_layout.this.subtitle
}

output "time" {
  description = "returns a string"
  value       = fortios_report_layout.this.time
}

output "title" {
  description = "returns a string"
  value       = fortios_report_layout.this.title
}

output "this" {
  value = fortios_report_layout.this
}
```

[top](#index)