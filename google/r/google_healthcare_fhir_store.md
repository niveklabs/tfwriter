# google_healthcare_fhir_store

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_healthcare_fhir_store" {
  source = "./modules/google/r/google_healthcare_fhir_store"

  # dataset - (required) is a type of string
  dataset = null
  # disable_referential_integrity - (optional) is a type of bool
  disable_referential_integrity = null
  # disable_resource_versioning - (optional) is a type of bool
  disable_resource_versioning = null
  # enable_history_import - (optional) is a type of bool
  enable_history_import = null
  # enable_update_create - (optional) is a type of bool
  enable_update_create = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # version - (required) is a type of string
  version = null

  notification_config = [{
    pubsub_topic = null
  }]

  stream_configs = [{
    bigquery_destination = [{
      dataset_uri = null
      schema_config = [{
        recursive_structure_depth = null
        schema_type               = null
      }]
    }]
    resource_types = []
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

variable "disable_referential_integrity" {
  description = "(optional) - Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store\ncreation. The default value is false, meaning that the API will enforce referential integrity and fail the\nrequests that will result in inconsistent state in the FHIR store. When this field is set to true, the API\nwill skip referential integrity check. Consequently, operations that rely on references, such as\nPatient.get$everything, will not return all the results if broken references exist.\n\n** Changing this property may recreate the FHIR store (removing all data) **"
  type        = bool
  default     = null
}

variable "disable_resource_versioning" {
  description = "(optional) - Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation\nof FHIR store. If set to false, which is the default behavior, all write operations will cause historical\nversions to be recorded automatically. The historical versions can be fetched through the history APIs, but\ncannot be updated. If set to true, no historical versions will be kept. The server will send back errors for\nattempts to read the historical versions.\n\n** Changing this property may recreate the FHIR store (removing all data) **"
  type        = bool
  default     = null
}

variable "enable_history_import" {
  description = "(optional) - Whether to allow the bulk import API to accept history bundles and directly insert historical resource\nversions into the FHIR store. Importing resource histories creates resource interactions that appear to have\noccurred in the past, which clients may not want to allow. If set to false, history bundles within an import\nwill fail with an error.\n\n** Changing this property may recreate the FHIR store (removing all data) **\n\n** This property can be changed manually in the Google Cloud Healthcare admin console without recreating the FHIR store **"
  type        = bool
  default     = null
}

variable "enable_update_create" {
  description = "(optional) - Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update\noperation to create a new resource with a client-specified ID. If false, all IDs are server-assigned through\nthe Create operation and attempts to Update a non-existent resource will return errors. Please treat the audit\nlogs with appropriate levels of care if client-specified resource IDs contain sensitive data such as patient\nidentifiers, those IDs will be part of the FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub\nnotifications."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - User-supplied key-value pairs used to organize FHIR stores.\n\nLabel keys must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128 bytes, and must\nconform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}][\\p{Ll}\\p{Lo}\\p{N}_-]{0,62}\n\nLabel values are optional, must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128\nbytes, and must conform to the following PCRE regular expression: [\\p{Ll}\\p{Lo}\\p{N}_-]{0,63}\n\nNo more than 64 labels can be associated with a given store.\n\nAn object containing a list of \"key\": value pairs.\nExample: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The resource name for the FhirStore.\n\n** Changing this property may recreate the FHIR store (removing all data) **"
  type        = string
}

variable "version" {
  description = "(required) - The FHIR specification version. Possible values: [\"DSTU2\", \"STU3\", \"R4\"]"
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

variable "stream_configs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bigquery_destination = list(object(
        {
          dataset_uri = string
          schema_config = list(object(
            {
              recursive_structure_depth = number
              schema_type               = string
            }
          ))
        }
      ))
      resource_types = list(string)
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
resource "google_healthcare_fhir_store" "this" {
  # dataset - (required) is a type of string
  dataset = var.dataset
  # disable_referential_integrity - (optional) is a type of bool
  disable_referential_integrity = var.disable_referential_integrity
  # disable_resource_versioning - (optional) is a type of bool
  disable_resource_versioning = var.disable_resource_versioning
  # enable_history_import - (optional) is a type of bool
  enable_history_import = var.enable_history_import
  # enable_update_create - (optional) is a type of bool
  enable_update_create = var.enable_update_create
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # version - (required) is a type of string
  version = var.version

  dynamic "notification_config" {
    for_each = var.notification_config
    content {
      # pubsub_topic - (required) is a type of string
      pubsub_topic = notification_config.value["pubsub_topic"]
    }
  }

  dynamic "stream_configs" {
    for_each = var.stream_configs
    content {
      # resource_types - (optional) is a type of list of string
      resource_types = stream_configs.value["resource_types"]

      dynamic "bigquery_destination" {
        for_each = stream_configs.value.bigquery_destination
        content {
          # dataset_uri - (required) is a type of string
          dataset_uri = bigquery_destination.value["dataset_uri"]

          dynamic "schema_config" {
            for_each = bigquery_destination.value.schema_config
            content {
              # recursive_structure_depth - (required) is a type of number
              recursive_structure_depth = schema_config.value["recursive_structure_depth"]
              # schema_type - (optional) is a type of string
              schema_type = schema_config.value["schema_type"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = google_healthcare_fhir_store.this.id
}

output "self_link" {
  description = "returns a string"
  value       = google_healthcare_fhir_store.this.self_link
}

output "this" {
  value = google_healthcare_fhir_store.this
}
```

[top](#index)