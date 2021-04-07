# google_api_gateway_api_config

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
module "google_api_gateway_api_config" {
  source = "./modules/google-beta/r/google_api_gateway_api_config"

  # api - (required) is a type of string
  api = null
  # api_config_id - (optional) is a type of string
  api_config_id = null
  # api_config_id_prefix - (optional) is a type of string
  api_config_id_prefix = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null

  gateway_config = [{
    backend_config = [{
      google_service_account = null
    }]
  }]

  openapi_documents = [{
    document = [{
      contents = null
      path     = null
    }]
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
variable "api" {
  description = "(required) - The API to attach the config to."
  type        = string
}

variable "api_config_id" {
  description = "(optional) - Identifier to assign to the API Config. Must be unique within scope of the parent resource(api)."
  type        = string
  default     = null
}

variable "api_config_id_prefix" {
  description = "(optional) - Creates a unique name beginning with the specified prefix. If this and api_config_id are unspecified, a random value is chosen for the name."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - A user-visible name for the API."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user-provided metadata."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      backend_config = list(object(
        {
          google_service_account = string
        }
      ))
    }
  ))
  default = []
}

variable "openapi_documents" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      document = list(object(
        {
          contents = string
          path     = string
        }
      ))
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
resource "google_api_gateway_api_config" "this" {
  # api - (required) is a type of string
  api = var.api
  # api_config_id - (optional) is a type of string
  api_config_id = var.api_config_id
  # api_config_id_prefix - (optional) is a type of string
  api_config_id_prefix = var.api_config_id_prefix
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # labels - (optional) is a type of map of string
  labels = var.labels
  # project - (optional) is a type of string
  project = var.project

  dynamic "gateway_config" {
    for_each = var.gateway_config
    content {

      dynamic "backend_config" {
        for_each = gateway_config.value.backend_config
        content {
          # google_service_account - (required) is a type of string
          google_service_account = backend_config.value["google_service_account"]
        }
      }

    }
  }

  dynamic "openapi_documents" {
    for_each = var.openapi_documents
    content {

      dynamic "document" {
        for_each = openapi_documents.value.document
        content {
          # contents - (required) is a type of string
          contents = document.value["contents"]
          # path - (required) is a type of string
          path = document.value["path"]
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
output "api_config_id" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.api_config_id
}

output "api_config_id_prefix" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.api_config_id_prefix
}

output "display_name" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.project
}

output "service_config_id" {
  description = "returns a string"
  value       = google_api_gateway_api_config.this.service_config_id
}

output "this" {
  value = google_api_gateway_api_config.this
}
```

[top](#index)