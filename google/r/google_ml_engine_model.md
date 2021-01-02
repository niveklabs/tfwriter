# google_ml_engine_model

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
module "google_ml_engine_model" {
  source = "./modules/google/r/google_ml_engine_model"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # online_prediction_console_logging - (optional) is a type of bool
  online_prediction_console_logging = null
  # online_prediction_logging - (optional) is a type of bool
  online_prediction_logging = null
  # project - (optional) is a type of string
  project = null
  # regions - (optional) is a type of list of string
  regions = []

  default_version = [{
    name = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The description specified for the model when it was created."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - One or more labels that you can add, to organize your models."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name specified for the model."
  type        = string
}

variable "online_prediction_console_logging" {
  description = "(optional) - If true, online prediction nodes send stderr and stdout streams to Stackdriver Logging"
  type        = bool
  default     = null
}

variable "online_prediction_logging" {
  description = "(optional) - If true, online prediction access logs are sent to StackDriver Logging."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "regions" {
  description = "(optional) - The list of regions where the model is going to be deployed.\nCurrently only one region per model is supported"
  type        = list(string)
  default     = null
}

variable "default_version" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_ml_engine_model" "this" {
  description                       = var.description
  labels                            = var.labels
  name                              = var.name
  online_prediction_console_logging = var.online_prediction_console_logging
  online_prediction_logging         = var.online_prediction_logging
  project                           = var.project
  regions                           = var.regions

  dynamic "default_version" {
    for_each = var.default_version
    content {
      name = default_version.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_ml_engine_model.this.id
}

output "project" {
  description = "returns a string"
  value       = google_ml_engine_model.this.project
}

output "this" {
  value = google_ml_engine_model.this
}
```

[top](#index)