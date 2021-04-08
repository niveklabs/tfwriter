# wavefront_external_link

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_external_link" {
  source = "./modules/wavefront/r/wavefront_external_link"

  # description - (required) is a type of string
  description = null
  # is_log_integration - (optional) is a type of bool
  is_log_integration = null
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = null
  # name - (required) is a type of string
  name = null
  # point_tag_filter_regexes - (optional) is a type of map of string
  point_tag_filter_regexes = {}
  # source_filter_regex - (optional) is a type of string
  source_filter_regex = null
  # template - (required) is a type of string
  template = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "is_log_integration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "metric_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "point_tag_filter_regexes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_filter_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_external_link" "this" {
  # description - (required) is a type of string
  description = var.description
  # is_log_integration - (optional) is a type of bool
  is_log_integration = var.is_log_integration
  # metric_filter_regex - (optional) is a type of string
  metric_filter_regex = var.metric_filter_regex
  # name - (required) is a type of string
  name = var.name
  # point_tag_filter_regexes - (optional) is a type of map of string
  point_tag_filter_regexes = var.point_tag_filter_regexes
  # source_filter_regex - (optional) is a type of string
  source_filter_regex = var.source_filter_regex
  # template - (required) is a type of string
  template = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_external_link.this.id
}

output "this" {
  value = wavefront_external_link.this
}
```

[top](#index)