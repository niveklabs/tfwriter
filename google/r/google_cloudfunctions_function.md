# google_cloudfunctions_function

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_cloudfunctions_function" {
  source = "./modules/google/r/google_cloudfunctions_function"

  # available_memory_mb - (optional) is a type of number
  available_memory_mb = null
  # build_environment_variables - (optional) is a type of map of string
  build_environment_variables = {}
  # description - (optional) is a type of string
  description = null
  # entry_point - (optional) is a type of string
  entry_point = null
  # environment_variables - (optional) is a type of map of string
  environment_variables = {}
  # https_trigger_url - (optional) is a type of string
  https_trigger_url = null
  # ingress_settings - (optional) is a type of string
  ingress_settings = null
  # labels - (optional) is a type of map of string
  labels = {}
  # max_instances - (optional) is a type of number
  max_instances = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # runtime - (required) is a type of string
  runtime = null
  # service_account_email - (optional) is a type of string
  service_account_email = null
  # source_archive_bucket - (optional) is a type of string
  source_archive_bucket = null
  # source_archive_object - (optional) is a type of string
  source_archive_object = null
  # timeout - (optional) is a type of number
  timeout = null
  # trigger_http - (optional) is a type of bool
  trigger_http = null
  # vpc_connector - (optional) is a type of string
  vpc_connector = null
  # vpc_connector_egress_settings - (optional) is a type of string
  vpc_connector_egress_settings = null

  event_trigger = [{
    event_type = null
    failure_policy = [{
      retry = null
    }]
    resource = null
  }]

  source_repository = [{
    deployed_url = null
    url          = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "available_memory_mb" {
  description = "(optional) - Memory (in MB), available to the function. Default value is 256MB. Allowed values are: 128MB, 256MB, 512MB, 1024MB, and 2048MB."
  type        = number
  default     = null
}

variable "build_environment_variables" {
  description = "(optional) -  A set of key/value environment variable pairs available during build time."
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of the function."
  type        = string
  default     = null
}

variable "entry_point" {
  description = "(optional) - Name of the function that will be executed when the Google Cloud Function is triggered."
  type        = string
  default     = null
}

variable "environment_variables" {
  description = "(optional) - A set of key/value environment variable pairs to assign to the function."
  type        = map(string)
  default     = null
}

variable "https_trigger_url" {
  description = "(optional) - URL which triggers function execution. Returned only if trigger_http is used."
  type        = string
  default     = null
}

variable "ingress_settings" {
  description = "(optional) - String value that controls what traffic can reach the function. Allowed values are ALLOW_ALL and ALLOW_INTERNAL_ONLY. Changes to this field will recreate the cloud function."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to the function. Label keys must follow the requirements at https://cloud.google.com/resource-manager/docs/creating-managing-labels#requirements."
  type        = map(string)
  default     = null
}

variable "max_instances" {
  description = "(optional) - The limit on the maximum number of function instances that may coexist at a given time."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - A user-defined name of the function. Function names must be unique globally."
  type        = string
}

variable "project" {
  description = "(optional) - Project of the function. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region of function. Currently can be only \"us-central1\". If it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "runtime" {
  description = "(required) - The runtime in which the function is going to run. Eg. \"nodejs8\", \"nodejs10\", \"python37\", \"go111\"."
  type        = string
}

variable "service_account_email" {
  description = "(optional) -  If provided, the self-provided service account to run the function with."
  type        = string
  default     = null
}

variable "source_archive_bucket" {
  description = "(optional) - The GCS bucket containing the zip archive which contains the function."
  type        = string
  default     = null
}

variable "source_archive_object" {
  description = "(optional) - The source archive object (file) in archive bucket."
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - Timeout (in seconds) for the function. Default value is 60 seconds. Cannot be more than 540 seconds."
  type        = number
  default     = null
}

variable "trigger_http" {
  description = "(optional) - Boolean variable. Any HTTP request (of a supported type) to the endpoint will trigger function execution. Supported HTTP request types are: POST, PUT, GET, DELETE, and OPTIONS. Endpoint is returned as https_trigger_url. Cannot be used with trigger_bucket and trigger_topic."
  type        = bool
  default     = null
}

variable "vpc_connector" {
  description = "(optional) - The VPC Network Connector that this cloud function can connect to. It can be either the fully-qualified URI, or the short name of the network connector resource. The format of this field is projects/*/locations/*/connectors/*."
  type        = string
  default     = null
}

variable "vpc_connector_egress_settings" {
  description = "(optional) - The egress settings for the connector, controlling what traffic is diverted through it. Allowed values are ALL_TRAFFIC and PRIVATE_RANGES_ONLY. Defaults to PRIVATE_RANGES_ONLY. If unset, this field preserves the previously set value."
  type        = string
  default     = null
}

variable "event_trigger" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      event_type = string
      failure_policy = list(object(
        {
          retry = bool
        }
      ))
      resource = string
    }
  ))
  default = []
}

variable "source_repository" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      deployed_url = string
      url          = string
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
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_cloudfunctions_function" "this" {
  available_memory_mb           = var.available_memory_mb
  build_environment_variables   = var.build_environment_variables
  description                   = var.description
  entry_point                   = var.entry_point
  environment_variables         = var.environment_variables
  https_trigger_url             = var.https_trigger_url
  ingress_settings              = var.ingress_settings
  labels                        = var.labels
  max_instances                 = var.max_instances
  name                          = var.name
  project                       = var.project
  region                        = var.region
  runtime                       = var.runtime
  service_account_email         = var.service_account_email
  source_archive_bucket         = var.source_archive_bucket
  source_archive_object         = var.source_archive_object
  timeout                       = var.timeout
  trigger_http                  = var.trigger_http
  vpc_connector                 = var.vpc_connector
  vpc_connector_egress_settings = var.vpc_connector_egress_settings

  dynamic "event_trigger" {
    for_each = var.event_trigger
    content {
      event_type = event_trigger.value["event_type"]
      resource   = event_trigger.value["resource"]

      dynamic "failure_policy" {
        for_each = event_trigger.value.failure_policy
        content {
          retry = failure_policy.value["retry"]
        }
      }

    }
  }

  dynamic "source_repository" {
    for_each = var.source_repository
    content {
      url = source_repository.value["url"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "https_trigger_url" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.https_trigger_url
}

output "id" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.project
}

output "region" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.region
}

output "service_account_email" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.service_account_email
}

output "vpc_connector_egress_settings" {
  description = "returns a string"
  value       = google_cloudfunctions_function.this.vpc_connector_egress_settings
}

output "this" {
  value = google_cloudfunctions_function.this
}
```

[top](#index)