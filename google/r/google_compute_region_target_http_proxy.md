# google_compute_region_target_http_proxy

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
module "google_compute_region_target_http_proxy" {
  source = "./modules/google/r/google_compute_region_target_http_proxy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # url_map - (required) is a type of string
  url_map = null

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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created target https proxy should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "url_map" {
  description = "(required) - A reference to the RegionUrlMap resource that defines the mapping from URL\nto the BackendService."
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
resource "google_compute_region_target_http_proxy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # url_map - (required) is a type of string
  url_map = var.url_map

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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_region_target_http_proxy.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_target_http_proxy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_target_http_proxy.this.project
}

output "proxy_id" {
  description = "returns a number"
  value       = google_compute_region_target_http_proxy.this.proxy_id
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_target_http_proxy.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_target_http_proxy.this.self_link
}

output "this" {
  value = google_compute_region_target_http_proxy.this
}
```

[top](#index)