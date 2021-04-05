# google_bigquery_connection

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_bigquery_connection" {
  source = "./modules/google-beta/r/google_bigquery_connection"

  # connection_id - (optional) is a type of string
  connection_id = null
  # description - (optional) is a type of string
  description = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # location - (optional) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null

  cloud_sql = [{
    credential = [{
      password = null
      username = null
    }]
    database    = null
    instance_id = null
    type        = null
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
variable "connection_id" {
  description = "(optional) - Optional connection id that should be assigned to the created connection."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - A descriptive description for the connection"
  type        = string
  default     = null
}

variable "friendly_name" {
  description = "(optional) - A descriptive name for the connection"
  type        = string
  default     = null
}

variable "location" {
  description = "(optional) - The geographic location where the connection should reside.\nCloud SQL instance must be in the same location as the connection\nwith following exceptions: Cloud SQL us-central1 maps to BigQuery US, Cloud SQL europe-west1 maps to BigQuery EU.\nExamples: US, EU, asia-northeast1, us-central1, europe-west1. The default value is US."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_sql" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      credential = list(object(
        {
          password = string
          username = string
        }
      ))
      database    = string
      instance_id = string
      type        = string
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
resource "google_bigquery_connection" "this" {
  connection_id = var.connection_id
  description   = var.description
  friendly_name = var.friendly_name
  location      = var.location
  project       = var.project

  dynamic "cloud_sql" {
    for_each = var.cloud_sql
    content {
      database    = cloud_sql.value["database"]
      instance_id = cloud_sql.value["instance_id"]
      type        = cloud_sql.value["type"]

      dynamic "credential" {
        for_each = cloud_sql.value.credential
        content {
          password = credential.value["password"]
          username = credential.value["username"]
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
output "connection_id" {
  description = "returns a string"
  value       = google_bigquery_connection.this.connection_id
}

output "has_credential" {
  description = "returns a bool"
  value       = google_bigquery_connection.this.has_credential
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_connection.this.id
}

output "name" {
  description = "returns a string"
  value       = google_bigquery_connection.this.name
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_connection.this.project
}

output "this" {
  value = google_bigquery_connection.this
}
```

[top](#index)