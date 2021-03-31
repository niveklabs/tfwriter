# google_pubsub_topic

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_pubsub_topic" {
  source = "./modules/google-beta/d/google_pubsub_topic"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the topic."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_pubsub_topic" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_pubsub_topic.this.id
}

output "kms_key_name" {
  description = "returns a string"
  value       = data.google_pubsub_topic.this.kms_key_name
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_pubsub_topic.this.labels
}

output "message_storage_policy" {
  description = "returns a list of object"
  value       = data.google_pubsub_topic.this.message_storage_policy
}

output "this" {
  value = google_pubsub_topic.this
}
```

[top](#index)