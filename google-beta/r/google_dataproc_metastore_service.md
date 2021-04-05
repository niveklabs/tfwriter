# google_dataproc_metastore_service

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
module "google_dataproc_metastore_service" {
  source = "./modules/google-beta/r/google_dataproc_metastore_service"

  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # network - (optional) is a type of string
  network = null
  # port - (optional) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # service_id - (required) is a type of string
  service_id = null
  # tier - (optional) is a type of string
  tier = null

  hive_metastore_config = [{
    config_overrides = {}
    kerberos_config = [{
      keytab = [{
        cloud_secret = null
      }]
      krb5_config_gcs_uri = null
      principal           = null
    }]
    version = null
  }]

  maintenance_window = [{
    day_of_week = null
    hour_of_day = null
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
variable "labels" {
  description = "(optional) - User-defined labels for the metastore service."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - The  location where the autoscaling policy should reside.\nThe default value is 'global'."
  type        = string
  default     = null
}

variable "network" {
  description = "(optional) - The relative resource name of the VPC network on which the instance can be accessed. It is specified in the following form:\n\n\"projects/{projectNumber}/global/networks/{network_id}\"."
  type        = string
  default     = null
}

variable "port" {
  description = "(optional) - The TCP port at which the metastore service is reached. Default: 9083."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required) - The ID of the metastore service. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_),\nand hyphens (-). Cannot begin or end with underscore or hyphen. Must consist of between\n3 and 63 characters."
  type        = string
}

variable "tier" {
  description = "(optional) - The tier of the service. Possible values: [\"DEVELOPER\", \"ENTERPRISE\"]"
  type        = string
  default     = null
}

variable "hive_metastore_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      config_overrides = map(string)
      kerberos_config = list(object(
        {
          keytab = list(object(
            {
              cloud_secret = string
            }
          ))
          krb5_config_gcs_uri = string
          principal           = string
        }
      ))
      version = string
    }
  ))
  default = []
}

variable "maintenance_window" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      day_of_week = string
      hour_of_day = number
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
resource "google_dataproc_metastore_service" "this" {
  labels     = var.labels
  location   = var.location
  network    = var.network
  port       = var.port
  project    = var.project
  service_id = var.service_id
  tier       = var.tier

  dynamic "hive_metastore_config" {
    for_each = var.hive_metastore_config
    content {
      config_overrides = hive_metastore_config.value["config_overrides"]
      version          = hive_metastore_config.value["version"]

      dynamic "kerberos_config" {
        for_each = hive_metastore_config.value.kerberos_config
        content {
          krb5_config_gcs_uri = kerberos_config.value["krb5_config_gcs_uri"]
          principal           = kerberos_config.value["principal"]

          dynamic "keytab" {
            for_each = kerberos_config.value.keytab
            content {
              cloud_secret = keytab.value["cloud_secret"]
            }
          }

        }
      }

    }
  }

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      day_of_week = maintenance_window.value["day_of_week"]
      hour_of_day = maintenance_window.value["hour_of_day"]
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
output "artifact_gcs_uri" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.artifact_gcs_uri
}

output "endpoint_uri" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.endpoint_uri
}

output "id" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.id
}

output "name" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.name
}

output "network" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.network
}

output "port" {
  description = "returns a number"
  value       = google_dataproc_metastore_service.this.port
}

output "project" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.project
}

output "state" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.state
}

output "state_message" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.state_message
}

output "tier" {
  description = "returns a string"
  value       = google_dataproc_metastore_service.this.tier
}

output "this" {
  value = google_dataproc_metastore_service.this
}
```

[top](#index)