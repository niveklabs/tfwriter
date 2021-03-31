# google_compute_project_default_network_tier

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_project_default_network_tier" {
  source = "./modules/google/r/google_compute_project_default_network_tier"

  # network_tier - (required) is a type of string
  network_tier = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "network_tier" {
  description = "(required) - The default network tier to be configured for the project. This field can take the following values: PREMIUM or STANDARD."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_project_default_network_tier" "this" {
  network_tier = var.network_tier
  project      = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_compute_project_default_network_tier.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_project_default_network_tier.this.project
}

output "this" {
  value = google_compute_project_default_network_tier.this
}
```

[top](#index)