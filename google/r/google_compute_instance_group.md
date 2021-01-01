# google_compute_instance_group

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_compute_instance_group" {
  source = "./modules/google/r/google_compute_instance_group"

  # description - (optional) is a type of string
  description = null
  # instances - (optional) is a type of set of string
  instances = []
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null

  named_port = [{
    name = null
    port = null
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

```hcl
variable "description" {
  description = "(optional) - An optional textual description of the instance group."
  type        = string
  default     = null
}

variable "instances" {
  description = "(optional) - List of instances in the group. They should be given as self_link URLs. When adding instances they must all be in the same network and zone as the instance group."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of the instance group. Must be 1-63 characters long and comply with RFC1035. Supported characters include lowercase letters, numbers, and hyphens."
  type        = string
}

variable "network" {
  description = "(optional) - The URL of the network the instance group is in. If this is different from the network where the instances are in, the creation fails. Defaults to the network where the instances are in (if neither network nor instances is specified, this field will be blank)."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone that this instance group should be created in."
  type        = string
  default     = null
}

variable "named_port" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      port = number
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_compute_instance_group" "this" {
  description = var.description
  instances   = var.instances
  name        = var.name
  network     = var.network
  project     = var.project
  zone        = var.zone

  dynamic "named_port" {
    for_each = var.named_port
    content {
      name = named_port.value["name"]
      port = named_port.value["port"]
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

```hcl
output "id" {
  description = "returns a string"
  value       = google_compute_instance_group.this.id
}

output "instances" {
  description = "returns a set of string"
  value       = google_compute_instance_group.this.instances
}

output "network" {
  description = "returns a string"
  value       = google_compute_instance_group.this.network
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_instance_group.this.self_link
}

output "size" {
  description = "returns a number"
  value       = google_compute_instance_group.this.size
}

output "zone" {
  description = "returns a string"
  value       = google_compute_instance_group.this.zone
}

output "this" {
  value = google_compute_instance_group.this
}
```

[top](#index)