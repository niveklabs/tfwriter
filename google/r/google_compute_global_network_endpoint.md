# google_compute_global_network_endpoint

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
module "google_compute_global_network_endpoint" {
  source = "./modules/google/r/google_compute_global_network_endpoint"

  # fqdn - (optional) is a type of string
  fqdn = null
  # global_network_endpoint_group - (required) is a type of string
  global_network_endpoint_group = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # port - (required) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fqdn" {
  description = "(optional) - Fully qualified domain name of network endpoint.\nThis can only be specified when network_endpoint_type of the NEG is INTERNET_FQDN_PORT."
  type        = string
  default     = null
}

variable "global_network_endpoint_group" {
  description = "(required) - The global network endpoint group this endpoint is part of."
  type        = string
}

variable "ip_address" {
  description = "(optional) - IPv4 address external endpoint."
  type        = string
  default     = null
}

variable "port" {
  description = "(required) - Port number of the external endpoint."
  type        = number
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "google_compute_global_network_endpoint" "this" {
  fqdn                          = var.fqdn
  global_network_endpoint_group = var.global_network_endpoint_group
  ip_address                    = var.ip_address
  port                          = var.port
  project                       = var.project

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
  value       = google_compute_global_network_endpoint.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_global_network_endpoint.this.project
}

output "this" {
  value = google_compute_global_network_endpoint.this
}
```

[top](#index)