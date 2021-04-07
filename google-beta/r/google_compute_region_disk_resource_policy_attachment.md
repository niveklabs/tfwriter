# google_compute_region_disk_resource_policy_attachment

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
module "google_compute_region_disk_resource_policy_attachment" {
  source = "./modules/google-beta/r/google_compute_region_disk_resource_policy_attachment"

  # disk - (required) is a type of string
  disk = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disk" {
  description = "(required) - The name of the regional disk in which the resource policies are attached to."
  type        = string
}

variable "name" {
  description = "(required) - The resource policy to be attached to the disk for scheduling snapshot\ncreation. Do not specify the self link."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - A reference to the region where the disk resides."
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
resource "google_compute_region_disk_resource_policy_attachment" "this" {
  # disk - (required) is a type of string
  disk = var.disk
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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
  value       = google_compute_region_disk_resource_policy_attachment.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_disk_resource_policy_attachment.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_disk_resource_policy_attachment.this.region
}

output "this" {
  value = google_compute_region_disk_resource_policy_attachment.this
}
```

[top](#index)