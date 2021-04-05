# google_compute_machine_image

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
module "google_compute_machine_image" {
  source = "./modules/google-beta/r/google_compute_machine_image"

  # description - (optional) is a type of string
  description = null
  # guest_flush - (optional) is a type of bool
  guest_flush = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # source_instance - (required) is a type of string
  source_instance = null

  machine_image_encryption_key = [{
    kms_key_name            = null
    kms_key_service_account = null
    raw_key                 = null
    sha256                  = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - A text description of the resource."
  type        = string
  default     = null
}

variable "guest_flush" {
  description = "(optional) - Specify this to create an application consistent machine image by informing the OS to prepare for the snapshot process.\nCurrently only supported on Windows instances using the Volume Shadow Copy Service (VSS)."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_instance" {
  description = "(required) - The source instance used to create the machine image. You can provide this as a partial or full URL to the resource."
  type        = string
}

variable "machine_image_encryption_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_name            = string
      kms_key_service_account = string
      raw_key                 = string
      sha256                  = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_machine_image" "this" {
  description     = var.description
  guest_flush     = var.guest_flush
  name            = var.name
  project         = var.project
  source_instance = var.source_instance

  dynamic "machine_image_encryption_key" {
    for_each = var.machine_image_encryption_key
    content {
      kms_key_service_account = machine_image_encryption_key.value["kms_key_service_account"]
      raw_key                 = machine_image_encryption_key.value["raw_key"]
    }
  }

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
  value       = google_compute_machine_image.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_machine_image.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_machine_image.this.self_link
}

output "storage_locations" {
  description = "returns a list of string"
  value       = google_compute_machine_image.this.storage_locations
}

output "this" {
  value = google_compute_machine_image.this
}
```

[top](#index)