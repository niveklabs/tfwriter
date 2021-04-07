# sumologic_cloudtrail_source

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
module "sumologic_cloudtrail_source" {
  source = "./modules/sumologic/r/sumologic_cloudtrail_source"

  # automatic_date_parsing - (optional) is a type of bool
  automatic_date_parsing = null
  # category - (optional) is a type of string
  category = null
  # collector_id - (required) is a type of number
  collector_id = null
  # content_type - (required) is a type of string
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
  # multiline_processing_enabled - (optional) is a type of bool
  multiline_processing_enabled = null
  # name - (required) is a type of string
  name = null
  # paused - (required) is a type of bool
  paused = null
  # scan_interval - (required) is a type of number
  scan_interval = null
  # timezone - (optional) is a type of string
  timezone = null
  # use_autoline_matching - (optional) is a type of bool
  use_autoline_matching = null

  authentication = [{
    access_key = null
    role_arn   = null
    secret_key = null
    type       = null
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
    bucket_name         = null
    limit_to_namespaces = []
    limit_to_regions    = []
    path_expression     = null
    tag_filters = [{
      namespace = null
      tags      = []
      type      = null
    }]
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
  description = "(required)"
  type        = string
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

variable "multiline_processing_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "paused" {
  description = "(required)"
  type        = bool
}

variable "scan_interval" {
  description = "(required)"
  type        = number
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
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_key = string
      role_arn   = string
      secret_key = string
      type       = string
    }
  ))
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
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket_name         = string
      limit_to_namespaces = list(string)
      limit_to_regions    = list(string)
      path_expression     = string
      tag_filters = list(object(
        {
          namespace = string
          tags      = list(string)
          type      = string
        }
      ))
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_cloudtrail_source" "this" {
  # automatic_date_parsing - (optional) is a type of bool
  automatic_date_parsing = var.automatic_date_parsing
  # category - (optional) is a type of string
  category = var.category
  # collector_id - (required) is a type of number
  collector_id = var.collector_id
  # content_type - (required) is a type of string
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
  # multiline_processing_enabled - (optional) is a type of bool
  multiline_processing_enabled = var.multiline_processing_enabled
  # name - (required) is a type of string
  name = var.name
  # paused - (required) is a type of bool
  paused = var.paused
  # scan_interval - (required) is a type of number
  scan_interval = var.scan_interval
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # use_autoline_matching - (optional) is a type of bool
  use_autoline_matching = var.use_autoline_matching

  dynamic "authentication" {
    for_each = var.authentication
    content {
      # access_key - (optional) is a type of string
      access_key = authentication.value["access_key"]
      # role_arn - (optional) is a type of string
      role_arn = authentication.value["role_arn"]
      # secret_key - (optional) is a type of string
      secret_key = authentication.value["secret_key"]
      # type - (required) is a type of string
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
      # bucket_name - (optional) is a type of string
      bucket_name = path.value["bucket_name"]
      # limit_to_namespaces - (optional) is a type of list of string
      limit_to_namespaces = path.value["limit_to_namespaces"]
      # limit_to_regions - (optional) is a type of list of string
      limit_to_regions = path.value["limit_to_regions"]
      # path_expression - (optional) is a type of string
      path_expression = path.value["path_expression"]
      # type - (required) is a type of string
      type = path.value["type"]

      dynamic "tag_filters" {
        for_each = path.value.tag_filters
        content {
          # namespace - (optional) is a type of string
          namespace = tag_filters.value["namespace"]
          # tags - (optional) is a type of list of string
          tags = tag_filters.value["tags"]
          # type - (optional) is a type of string
          type = tag_filters.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_cloudtrail_source.this.id
}

output "url" {
  description = "returns a string"
  value       = sumologic_cloudtrail_source.this.url
}

output "this" {
  value = sumologic_cloudtrail_source.this
}
```

[top](#index)