# google_compute_router

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
module "google_compute_router" {
  source = "./modules/google-beta/r/google_compute_router"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  bgp = [{
    advertise_mode    = null
    advertised_groups = []
    advertised_ip_ranges = [{
      description = null
      range       = null
    }]
    asn = null
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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. The name must be 1-63 characters long, and\ncomply with RFC1035. Specifically, the name must be 1-63 characters\nlong and match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?'\nwhich means the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(required) - A reference to the network to which this router belongs."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the router resides."
  type        = string
  default     = null
}

variable "bgp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      advertise_mode    = string
      advertised_groups = list(string)
      advertised_ip_ranges = list(object(
        {
          description = string
          range       = string
        }
      ))
      asn = number
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
resource "google_compute_router" "this" {
  description = var.description
  name        = var.name
  network     = var.network
  project     = var.project
  region      = var.region

  dynamic "bgp" {
    for_each = var.bgp
    content {
      advertise_mode    = bgp.value["advertise_mode"]
      advertised_groups = bgp.value["advertised_groups"]
      asn               = bgp.value["asn"]

      dynamic "advertised_ip_ranges" {
        for_each = bgp.value.advertised_ip_ranges
        content {
          description = advertised_ip_ranges.value["description"]
          range       = advertised_ip_ranges.value["range"]
        }
      }

    }
  }

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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_router.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_router.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_router.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_router.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_router.this.self_link
}

output "this" {
  value = google_compute_router.this
}
```

[top](#index)