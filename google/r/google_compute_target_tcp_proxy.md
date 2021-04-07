# google_compute_target_tcp_proxy

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
module "google_compute_target_tcp_proxy" {
  source = "./modules/google/r/google_compute_target_tcp_proxy"

  # backend_service - (required) is a type of string
  backend_service = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # proxy_bind - (optional) is a type of bool
  proxy_bind = null
  # proxy_header - (optional) is a type of string
  proxy_header = null

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
variable "backend_service" {
  description = "(required) - A reference to the BackendService resource."
  type        = string
}

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

variable "proxy_bind" {
  description = "(optional) - This field only applies when the forwarding rule that references\nthis target proxy has a loadBalancingScheme set to INTERNAL_SELF_MANAGED."
  type        = bool
  default     = null
}

variable "proxy_header" {
  description = "(optional) - Specifies the type of proxy header to append before sending data to\nthe backend. Default value: \"NONE\" Possible values: [\"NONE\", \"PROXY_V1\"]"
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
resource "google_compute_target_tcp_proxy" "this" {
  # backend_service - (required) is a type of string
  backend_service = var.backend_service
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # proxy_bind - (optional) is a type of bool
  proxy_bind = var.proxy_bind
  # proxy_header - (optional) is a type of string
  proxy_header = var.proxy_header

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
  value       = google_compute_target_tcp_proxy.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_target_tcp_proxy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_target_tcp_proxy.this.project
}

output "proxy_bind" {
  description = "returns a bool"
  value       = google_compute_target_tcp_proxy.this.proxy_bind
}

output "proxy_id" {
  description = "returns a number"
  value       = google_compute_target_tcp_proxy.this.proxy_id
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_target_tcp_proxy.this.self_link
}

output "this" {
  value = google_compute_target_tcp_proxy.this
}
```

[top](#index)