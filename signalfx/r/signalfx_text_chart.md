# signalfx_text_chart

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_text_chart" {
  source = "./modules/signalfx/r/signalfx_text_chart"

  # description - (optional) is a type of string
  description = null
  # markdown - (required) is a type of string
  markdown = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the chart (Optional)"
  type        = string
  default     = null
}

variable "markdown" {
  description = "(required) - Markdown text to display. More info at: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
  type        = string
}

variable "name" {
  description = "(required) - Name of the chart"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_text_chart" "this" {
  # description - (optional) is a type of string
  description = var.description
  # markdown - (required) is a type of string
  markdown = var.markdown
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_text_chart.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_text_chart.this.url
}

output "this" {
  value = signalfx_text_chart.this
}
```

[top](#index)