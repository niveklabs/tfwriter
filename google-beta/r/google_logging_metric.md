# google_logging_metric

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_logging_metric" {
  source = "./modules/google-beta/r/google_logging_metric"

  # description - (optional) is a type of string
  description = null
  # filter - (required) is a type of string
  filter = null
  # label_extractors - (optional) is a type of map of string
  label_extractors = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # value_extractor - (optional) is a type of string
  value_extractor = null

  bucket_options = [{
    explicit_buckets = [{
      bounds = []
    }]
    exponential_buckets = [{
      growth_factor      = null
      num_finite_buckets = null
      scale              = null
    }]
    linear_buckets = [{
      num_finite_buckets = null
      offset             = null
      width              = null
    }]
  }]

  metric_descriptor = [{
    display_name = null
    labels = [{
      description = null
      key         = null
      value_type  = null
    }]
    metric_kind = null
    unit        = null
    value_type  = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A description of this metric, which is used in documentation. The maximum length of the\ndescription is 8000 characters."
  type        = string
  default     = null
}

variable "filter" {
  description = "(required) - An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which\nis used to match log entries."
  type        = string
}

variable "label_extractors" {
  description = "(optional) - A map from a label key string to an extractor expression which is used to extract data from a log\nentry field and assign as the label value. Each label key specified in the LabelDescriptor must\nhave an associated extractor expression in this map. The syntax of the extractor expression is\nthe same as for the valueExtractor field."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The client-assigned metric identifier. Examples - \"error_count\", \"nginx/requests\".\nMetric identifiers are limited to 100 characters and can include only the following\ncharacters A-Z, a-z, 0-9, and the special characters _-.,+!*',()%/. The forward-slash\ncharacter (/) denotes a hierarchy of name pieces, and it cannot be the first character\nof the name."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value_extractor" {
  description = "(optional) - A valueExtractor is required when using a distribution logs-based metric to extract the values to\nrecord from a log entry. Two functions are supported for value extraction - EXTRACT(field) or\nREGEXP_EXTRACT(field, regex). The argument are 1. field - The name of the log entry field from which\nthe value is to be extracted. 2. regex - A regular expression using the Google RE2 syntax\n(https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from the specified\nlog entry field. The value of the field is converted to a string before applying the regex. It is an\nerror to specify a regex that does not include exactly one capture group."
  type        = string
  default     = null
}

variable "bucket_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      explicit_buckets = list(object(
        {
          bounds = list(number)
        }
      ))
      exponential_buckets = list(object(
        {
          growth_factor      = number
          num_finite_buckets = number
          scale              = number
        }
      ))
      linear_buckets = list(object(
        {
          num_finite_buckets = number
          offset             = number
          width              = number
        }
      ))
    }
  ))
  default = []
}

variable "metric_descriptor" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      display_name = string
      labels = set(object(
        {
          description = string
          key         = string
          value_type  = string
        }
      ))
      metric_kind = string
      unit        = string
      value_type  = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_logging_metric" "this" {
  description      = var.description
  filter           = var.filter
  label_extractors = var.label_extractors
  name             = var.name
  project          = var.project
  value_extractor  = var.value_extractor

  dynamic "bucket_options" {
    for_each = var.bucket_options
    content {

      dynamic "explicit_buckets" {
        for_each = bucket_options.value.explicit_buckets
        content {
          bounds = explicit_buckets.value["bounds"]
        }
      }

      dynamic "exponential_buckets" {
        for_each = bucket_options.value.exponential_buckets
        content {
          growth_factor      = exponential_buckets.value["growth_factor"]
          num_finite_buckets = exponential_buckets.value["num_finite_buckets"]
          scale              = exponential_buckets.value["scale"]
        }
      }

      dynamic "linear_buckets" {
        for_each = bucket_options.value.linear_buckets
        content {
          num_finite_buckets = linear_buckets.value["num_finite_buckets"]
          offset             = linear_buckets.value["offset"]
          width              = linear_buckets.value["width"]
        }
      }

    }
  }

  dynamic "metric_descriptor" {
    for_each = var.metric_descriptor
    content {
      display_name = metric_descriptor.value["display_name"]
      metric_kind  = metric_descriptor.value["metric_kind"]
      unit         = metric_descriptor.value["unit"]
      value_type   = metric_descriptor.value["value_type"]

      dynamic "labels" {
        for_each = metric_descriptor.value.labels
        content {
          description = labels.value["description"]
          key         = labels.value["key"]
          value_type  = labels.value["value_type"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_logging_metric.this.id
}

output "project" {
  description = "returns a string"
  value       = google_logging_metric.this.project
}

output "this" {
  value = google_logging_metric.this
}
```

[top](#index)