# google_service_directory_endpoint

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
module "google_service_directory_endpoint" {
  source = "./modules/google-beta/r/google_service_directory_endpoint"

  # address - (optional) is a type of string
  address = null
  # endpoint_id - (required) is a type of string
  endpoint_id = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # port - (optional) is a type of number
  port = null
  # service - (required) is a type of string
  service = null

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
variable "address" {
  description = "(optional) - IPv4 or IPv6 address of the endpoint."
  type        = string
  default     = null
}

variable "endpoint_id" {
  description = "(required) - The Resource ID must be 1-63 characters long, including digits,\nlowercase letters or the hyphen character."
  type        = string
}

variable "metadata" {
  description = "(optional) - Metadata for the endpoint. This data can be consumed\nby service clients. The entire metadata dictionary may contain\nup to 512 characters, spread across all key-value pairs.\nMetadata that goes beyond any these limits will be rejected."
  type        = map(string)
  default     = null
}

variable "port" {
  description = "(optional) - Port that the endpoint is running on, must be in the\nrange of [0, 65535]. If unspecified, the default is 0."
  type        = number
  default     = null
}

variable "service" {
  description = "(required) - The resource name of the service that this endpoint provides."
  type        = string
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
resource "google_service_directory_endpoint" "this" {
  address     = var.address
  endpoint_id = var.endpoint_id
  metadata    = var.metadata
  port        = var.port
  service     = var.service

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
  value       = google_service_directory_endpoint.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_directory_endpoint.this.name
}

output "this" {
  value = google_service_directory_endpoint.this
}
```

[top](#index)