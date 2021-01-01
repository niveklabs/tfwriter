# google_kms_key_ring

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
module "google_kms_key_ring" {
  source = "./modules/google/r/google_kms_key_ring"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
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

```hcl
variable "location" {
  description = "(required) - The location for the KeyRing.\nA full list of valid locations can be found by running 'gcloud kms locations list'."
  type        = string
}

variable "name" {
  description = "(required) - The resource name for the KeyRing."
  type        = string
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

```hcl
resource "google_kms_key_ring" "this" {
  location = var.location
  name     = var.name
  project  = var.project

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_kms_key_ring.this.id
}

output "project" {
  description = "returns a string"
  value       = google_kms_key_ring.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_kms_key_ring.this.self_link
}

output "this" {
  value = google_kms_key_ring.this
}
```

[top](#index)