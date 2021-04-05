# google_healthcare_dataset

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
module "google_healthcare_dataset" {
  source = "./modules/google/r/google_healthcare_dataset"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # time_zone - (optional) is a type of string
  time_zone = null

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
variable "location" {
  description = "(required) - The location for the Dataset."
  type        = string
}

variable "name" {
  description = "(required) - The resource name for the Dataset."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_zone" {
  description = "(optional) - The default timezone used by this dataset. Must be a either a valid IANA time zone name such as\n\"America/New_York\" or empty, which defaults to UTC. This is used for parsing times in resources\n(e.g., HL7 messages) where no explicit timezone is specified."
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
resource "google_healthcare_dataset" "this" {
  location  = var.location
  name      = var.name
  project   = var.project
  time_zone = var.time_zone

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
  value       = google_healthcare_dataset.this.id
}

output "project" {
  description = "returns a string"
  value       = google_healthcare_dataset.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_healthcare_dataset.this.self_link
}

output "time_zone" {
  description = "returns a string"
  value       = google_healthcare_dataset.this.time_zone
}

output "this" {
  value = google_healthcare_dataset.this
}
```

[top](#index)