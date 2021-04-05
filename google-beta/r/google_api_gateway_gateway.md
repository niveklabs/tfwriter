# google_api_gateway_gateway

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
module "google_api_gateway_gateway" {
  source = "./modules/google-beta/r/google_api_gateway_gateway"

  # api_config - (required) is a type of string
  api_config = null
  # display_name - (optional) is a type of string
  display_name = null
  # gateway_id - (required) is a type of string
  gateway_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

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
variable "api_config" {
  description = "(required) - Resource name of the API Config for this Gateway. Format: projects/{project}/locations/global/apis/{api}/configs/{apiConfig}"
  type        = string
}

variable "display_name" {
  description = "(optional) - A user-visible name for the API."
  type        = string
  default     = null
}

variable "gateway_id" {
  description = "(required) - Identifier to assign to the Gateway. Must be unique within scope of the parent resource(project)."
  type        = string
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

variable "region" {
  description = "(optional) - The region of the gateway for the API."
  type        = string
  default     = null
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
resource "google_api_gateway_gateway" "this" {
  api_config   = var.api_config
  display_name = var.display_name
  gateway_id   = var.gateway_id
  labels       = var.labels
  project      = var.project
  region       = var.region

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
output "default_hostname" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.default_hostname
}

output "display_name" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.id
}

output "name" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.name
}

output "project" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.project
}

output "region" {
  description = "returns a string"
  value       = google_api_gateway_gateway.this.region
}

output "this" {
  value = google_api_gateway_gateway.this
}
```

[top](#index)