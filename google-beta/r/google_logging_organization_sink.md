# google_logging_organization_sink

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_logging_organization_sink" {
  source = "./modules/google-beta/r/google_logging_organization_sink"

  # description - (optional) is a type of string
  description = null
  # destination - (required) is a type of string
  destination = null
  # disabled - (optional) is a type of bool
  disabled = null
  # filter - (optional) is a type of string
  filter = null
  # include_children - (optional) is a type of bool
  include_children = null
  # name - (required) is a type of string
  name = null
  # org_id - (required) is a type of string
  org_id = null

  bigquery_options = [{
    use_partitioned_tables = null
  }]

  exclusions = [{
    description = null
    disabled    = null
    filter      = null
    name        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A description of this sink. The maximum length of the description is 8000 characters."
  type        = string
  default     = null
}

variable "destination" {
  description = "(required) - The destination of the sink (or, in other words, where logs are written to). Can be a Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples: \"storage.googleapis.com/[GCS_BUCKET]\" \"bigquery.googleapis.com/projects/[PROJECT_ID]/datasets/[DATASET]\" \"pubsub.googleapis.com/projects/[PROJECT_ID]/topics/[TOPIC_ID]\" The writer associated with the sink must have access to write to the above resource."
  type        = string
}

variable "disabled" {
  description = "(optional) - If set to True, then this sink is disabled and it does not export any log entries."
  type        = bool
  default     = null
}

variable "filter" {
  description = "(optional) - The filter to apply when exporting logs. Only log entries that match the filter are exported."
  type        = string
  default     = null
}

variable "include_children" {
  description = "(optional) - Whether or not to include children organizations in the sink export. If true, logs associated with child projects are also exported; otherwise only logs relating to the provided organization are included."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the logging sink."
  type        = string
}

variable "org_id" {
  description = "(required) - The numeric ID of the organization to be exported to the sink."
  type        = string
}

variable "bigquery_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      use_partitioned_tables = bool
    }
  ))
  default = []
}

variable "exclusions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      disabled    = bool
      filter      = string
      name        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_logging_organization_sink" "this" {
  description      = var.description
  destination      = var.destination
  disabled         = var.disabled
  filter           = var.filter
  include_children = var.include_children
  name             = var.name
  org_id           = var.org_id

  dynamic "bigquery_options" {
    for_each = var.bigquery_options
    content {
      use_partitioned_tables = bigquery_options.value["use_partitioned_tables"]
    }
  }

  dynamic "exclusions" {
    for_each = var.exclusions
    content {
      description = exclusions.value["description"]
      disabled    = exclusions.value["disabled"]
      filter      = exclusions.value["filter"]
      name        = exclusions.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_logging_organization_sink.this.id
}

output "writer_identity" {
  description = "returns a string"
  value       = google_logging_organization_sink.this.writer_identity
}

output "this" {
  value = google_logging_organization_sink.this
}
```

[top](#index)