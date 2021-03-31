# google_healthcare_hl7_v2_store

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_healthcare_hl7_v2_store" {
  source = "./modules/google/r/google_healthcare_hl7_v2_store"

  # dataset - (required) is a type of string
  dataset = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null

  notification_config = [{
    pubsub_topic = null
  }]

  notification_configs = [{
    filter       = null
    pubsub_topic = null
  }]

  parser_config = [{
    allow_null_header  = null
    schema             = null
    segment_terminator = null
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
variable "dataset" {
  description = "(required) - Identifies the dataset addressed by this request. Must be in the format\n'projects/{project}/locations/{location}/datasets/{dataset}'"
  type        = string
}

variable "labels" {
  description = "(optional) - User-supplied key-value pairs used to organize HL7v2 stores.\n\nLabel keys must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128 bytes, and must\nconform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}][\\p{Ll}\\p{Lo}\\p{N}_-]{0,62}\n\nLabel values are optional, must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128\nbytes, and must conform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}\\p{N}_-]{0,63}\n\nNo more than 64 labels can be associated with a given store.\n\nAn object containing a list of \"key\": value pairs.\nExample: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The resource name for the Hl7V2Store.\n\n** Changing this property may recreate the Hl7v2 store (removing all data) **"
  type        = string
}

variable "notification_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      pubsub_topic = string
    }
  ))
  default = []
}

variable "notification_configs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter       = string
      pubsub_topic = string
    }
  ))
  default = []
}

variable "parser_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_null_header  = bool
      schema             = string
      segment_terminator = string
    }
  ))
  default = []
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
resource "google_healthcare_hl7_v2_store" "this" {
  dataset = var.dataset
  labels  = var.labels
  name    = var.name

  dynamic "notification_config" {
    for_each = var.notification_config
    content {
      pubsub_topic = notification_config.value["pubsub_topic"]
    }
  }

  dynamic "notification_configs" {
    for_each = var.notification_configs
    content {
      filter       = notification_configs.value["filter"]
      pubsub_topic = notification_configs.value["pubsub_topic"]
    }
  }

  dynamic "parser_config" {
    for_each = var.parser_config
    content {
      allow_null_header  = parser_config.value["allow_null_header"]
      schema             = parser_config.value["schema"]
      segment_terminator = parser_config.value["segment_terminator"]
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
  value       = google_healthcare_hl7_v2_store.this.id
}

output "self_link" {
  description = "returns a string"
  value       = google_healthcare_hl7_v2_store.this.self_link
}

output "this" {
  value = google_healthcare_hl7_v2_store.this
}
```

[top](#index)