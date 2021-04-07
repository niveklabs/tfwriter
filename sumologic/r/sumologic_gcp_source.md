# sumologic_gcp_source

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_gcp_source" {
  source = "./modules/sumologic/r/sumologic_gcp_source"

  # automatic_date_parsing - (optional) is a type of bool
  automatic_date_parsing = null
  # category - (optional) is a type of string
  category = null
  # collector_id - (required) is a type of number
  collector_id = null
  # content_type - (optional) is a type of string
  content_type = null
  # cutoff_relative_time - (optional) is a type of string
  cutoff_relative_time = null
  # cutoff_timestamp - (optional) is a type of number
  cutoff_timestamp = null
  # description - (optional) is a type of string
  description = null
  # fields - (optional) is a type of map of string
  fields = {}
  # force_timezone - (optional) is a type of bool
  force_timezone = null
  # host_name - (optional) is a type of string
  host_name = null
  # manual_prefix_regexp - (optional) is a type of string
  manual_prefix_regexp = null
  # message_per_request - (optional) is a type of bool
  message_per_request = null
  # multiline_processing_enabled - (optional) is a type of bool
  multiline_processing_enabled = null
  # name - (required) is a type of string
  name = null
  # timezone - (optional) is a type of string
  timezone = null
  # use_autoline_matching - (optional) is a type of bool
  use_autoline_matching = null

  authentication = [{
    type = null
  }]

  default_date_formats = [{
    format  = null
    locator = null
  }]

  filters = [{
    filter_type = null
    mask        = null
    name        = null
    regexp      = null
  }]

  path = [{
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "automatic_date_parsing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "collector_id" {
  description = "(required)"
  type        = number
}

variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cutoff_relative_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cutoff_timestamp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fields" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "force_timezone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "host_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "manual_prefix_regexp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "message_per_request" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "multiline_processing_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_autoline_matching" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "default_date_formats" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      format  = string
      locator = string
    }
  ))
  default = []
}

variable "filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter_type = string
      mask        = string
      name        = string
      regexp      = string
    }
  ))
  default = []
}

variable "path" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_gcp_source" "this" {
  # automatic_date_parsing - (optional) is a type of bool
  automatic_date_parsing = var.automatic_date_parsing
  # category - (optional) is a type of string
  category = var.category
  # collector_id - (required) is a type of number
  collector_id = var.collector_id
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # cutoff_relative_time - (optional) is a type of string
  cutoff_relative_time = var.cutoff_relative_time
  # cutoff_timestamp - (optional) is a type of number
  cutoff_timestamp = var.cutoff_timestamp
  # description - (optional) is a type of string
  description = var.description
  # fields - (optional) is a type of map of string
  fields = var.fields
  # force_timezone - (optional) is a type of bool
  force_timezone = var.force_timezone
  # host_name - (optional) is a type of string
  host_name = var.host_name
  # manual_prefix_regexp - (optional) is a type of string
  manual_prefix_regexp = var.manual_prefix_regexp
  # message_per_request - (optional) is a type of bool
  message_per_request = var.message_per_request
  # multiline_processing_enabled - (optional) is a type of bool
  multiline_processing_enabled = var.multiline_processing_enabled
  # name - (required) is a type of string
  name = var.name
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # use_autoline_matching - (optional) is a type of bool
  use_autoline_matching = var.use_autoline_matching

  dynamic "authentication" {
    for_each = var.authentication
    content {
      # type - (optional) is a type of string
      type = authentication.value["type"]
    }
  }

  dynamic "default_date_formats" {
    for_each = var.default_date_formats
    content {
      # format - (required) is a type of string
      format = default_date_formats.value["format"]
      # locator - (optional) is a type of string
      locator = default_date_formats.value["locator"]
    }
  }

  dynamic "filters" {
    for_each = var.filters
    content {
      # filter_type - (required) is a type of string
      filter_type = filters.value["filter_type"]
      # mask - (optional) is a type of string
      mask = filters.value["mask"]
      # name - (required) is a type of string
      name = filters.value["name"]
      # regexp - (required) is a type of string
      regexp = filters.value["regexp"]
    }
  }

  dynamic "path" {
    for_each = var.path
    content {
      # type - (optional) is a type of string
      type = path.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_gcp_source.this.id
}

output "url" {
  description = "returns a string"
  value       = sumologic_gcp_source.this.url
}

output "this" {
  value = sumologic_gcp_source.this
}
```

[top](#index)