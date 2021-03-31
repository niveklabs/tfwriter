# google_compute_network_endpoint

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_network_endpoint" {
  source = "./modules/google-beta/r/google_compute_network_endpoint"

  # instance - (required) is a type of string
  instance = null
  # ip_address - (required) is a type of string
  ip_address = null
  # network_endpoint_group - (required) is a type of string
  network_endpoint_group = null
  # port - (required) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance" {
  description = "(required) - The name for a specific VM instance that the IP address belongs to.\nThis is required for network endpoints of type GCE_VM_IP_PORT.\nThe instance must be in the same zone of network endpoint group."
  type        = string
}

variable "ip_address" {
  description = "(required) - IPv4 address of network endpoint. The IP address must belong\nto a VM in GCE (either the primary IP or as part of an aliased IP\nrange)."
  type        = string
}

variable "network_endpoint_group" {
  description = "(required) - The network endpoint group this endpoint is part of."
  type        = string
}

variable "port" {
  description = "(required) - Port number of network endpoint."
  type        = number
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Zone where the containing network endpoint group is located."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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
resource "google_compute_network_endpoint" "this" {
  instance               = var.instance
  ip_address             = var.ip_address
  network_endpoint_group = var.network_endpoint_group
  port                   = var.port
  project                = var.project
  zone                   = var.zone

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
  value       = google_compute_network_endpoint.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_network_endpoint.this.project
}

output "zone" {
  description = "returns a string"
  value       = google_compute_network_endpoint.this.zone
}

output "this" {
  value = google_compute_network_endpoint.this
}
```

[top](#index)