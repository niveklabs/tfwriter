# google_compute_packet_mirroring

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
module "google_compute_packet_mirroring" {
  source = "./modules/google-beta/r/google_compute_packet_mirroring"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  collector_ilb = [{
    url = null
  }]

  filter = [{
    cidr_ranges  = []
    direction    = null
    ip_protocols = []
  }]

  mirrored_resources = [{
    instances = [{
      url = null
    }]
    subnetworks = [{
      url = null
    }]
    tags = []
  }]

  network = [{
    url = null
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
  description = "(optional) - A human-readable description of the rule."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the packet mirroring rule"
  type        = string
}

variable "priority" {
  description = "(optional) - Since only one rule can be active at a time, priority is\nused to break ties in the case of two rules that apply to\nthe same instances."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created address should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "collector_ilb" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      url = string
    }
  ))
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cidr_ranges  = list(string)
      direction    = string
      ip_protocols = list(string)
    }
  ))
  default = []
}

variable "mirrored_resources" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      instances = list(object(
        {
          url = string
        }
      ))
      subnetworks = list(object(
        {
          url = string
        }
      ))
      tags = list(string)
    }
  ))
}

variable "network" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      url = string
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
resource "google_compute_packet_mirroring" "this" {
  description = var.description
  name        = var.name
  priority    = var.priority
  project     = var.project
  region      = var.region

  dynamic "collector_ilb" {
    for_each = var.collector_ilb
    content {
      url = collector_ilb.value["url"]
    }
  }

  dynamic "filter" {
    for_each = var.filter
    content {
      cidr_ranges  = filter.value["cidr_ranges"]
      direction    = filter.value["direction"]
      ip_protocols = filter.value["ip_protocols"]
    }
  }

  dynamic "mirrored_resources" {
    for_each = var.mirrored_resources
    content {
      tags = mirrored_resources.value["tags"]

      dynamic "instances" {
        for_each = mirrored_resources.value.instances
        content {
          url = instances.value["url"]
        }
      }

      dynamic "subnetworks" {
        for_each = mirrored_resources.value.subnetworks
        content {
          url = subnetworks.value["url"]
        }
      }

    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      url = network.value["url"]
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
output "id" {
  description = "returns a string"
  value       = google_compute_packet_mirroring.this.id
}

output "priority" {
  description = "returns a number"
  value       = google_compute_packet_mirroring.this.priority
}

output "project" {
  description = "returns a string"
  value       = google_compute_packet_mirroring.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_packet_mirroring.this.region
}

output "this" {
  value = google_compute_packet_mirroring.this
}
```

[top](#index)