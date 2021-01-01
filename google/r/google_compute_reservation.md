# google_compute_reservation

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
module "google_compute_reservation" {
  source = "./modules/google/r/google_compute_reservation"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # specific_reservation_required - (optional) is a type of bool
  specific_reservation_required = null
  # zone - (required) is a type of string
  zone = null

  specific_reservation = [{
    count        = null
    in_use_count = null
    instance_properties = [{
      guest_accelerators = [{
        accelerator_count = null
        accelerator_type  = null
      }]
      local_ssds = [{
        disk_size_gb = null
        interface    = null
      }]
      machine_type     = null
      min_cpu_platform = null
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

```hcl
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

variable "specific_reservation_required" {
  description = "(optional) - When set to true, only VMs that target this reservation by name can\nconsume this reservation. Otherwise, it can be consumed by VMs with\naffinity for any reservation. Defaults to false."
  type        = bool
  default     = null
}

variable "zone" {
  description = "(required) - The zone where the reservation is made."
  type        = string
}

variable "specific_reservation" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      count        = number
      in_use_count = number
      instance_properties = list(object(
        {
          guest_accelerators = list(object(
            {
              accelerator_count = number
              accelerator_type  = string
            }
          ))
          local_ssds = list(object(
            {
              disk_size_gb = number
              interface    = string
            }
          ))
          machine_type     = string
          min_cpu_platform = string
        }
      ))
    }
  ))
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
resource "google_compute_reservation" "this" {
  description                   = var.description
  name                          = var.name
  project                       = var.project
  specific_reservation_required = var.specific_reservation_required
  zone                          = var.zone

  dynamic "specific_reservation" {
    for_each = var.specific_reservation
    content {
      count = specific_reservation.value["count"]

      dynamic "instance_properties" {
        for_each = specific_reservation.value.instance_properties
        content {
          machine_type     = instance_properties.value["machine_type"]
          min_cpu_platform = instance_properties.value["min_cpu_platform"]

          dynamic "guest_accelerators" {
            for_each = instance_properties.value.guest_accelerators
            content {
              accelerator_count = guest_accelerators.value["accelerator_count"]
              accelerator_type  = guest_accelerators.value["accelerator_type"]
            }
          }

          dynamic "local_ssds" {
            for_each = instance_properties.value.local_ssds
            content {
              disk_size_gb = local_ssds.value["disk_size_gb"]
              interface    = local_ssds.value["interface"]
            }
          }

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

```hcl
output "commitment" {
  description = "returns a string"
  value       = google_compute_reservation.this.commitment
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_reservation.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_reservation.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_reservation.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_reservation.this.self_link
}

output "status" {
  description = "returns a string"
  value       = google_compute_reservation.this.status
}

output "this" {
  value = google_compute_reservation.this
}
```

[top](#index)