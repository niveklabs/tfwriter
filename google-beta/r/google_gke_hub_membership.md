# google_gke_hub_membership

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
module "google_gke_hub_membership" {
  source = "./modules/google-beta/r/google_gke_hub_membership"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # membership_id - (required) is a type of string
  membership_id = null
  # project - (optional) is a type of string
  project = null

  authority = [{
    issuer = null
  }]

  endpoint = [{
    gke_cluster = [{
      resource_link = null
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

```terraform
variable "description" {
  description = "(optional) - The name of this entity type to be displayed on the console."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this membership."
  type        = map(string)
  default     = null
}

variable "membership_id" {
  description = "(required) - The client-provided identifier of the membership."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authority" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      issuer = string
    }
  ))
  default = []
}

variable "endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      gke_cluster = list(object(
        {
          resource_link = string
        }
      ))
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
resource "google_gke_hub_membership" "this" {
  description   = var.description
  labels        = var.labels
  membership_id = var.membership_id
  project       = var.project

  dynamic "authority" {
    for_each = var.authority
    content {
      issuer = authority.value["issuer"]
    }
  }

  dynamic "endpoint" {
    for_each = var.endpoint
    content {

      dynamic "gke_cluster" {
        for_each = endpoint.value.gke_cluster
        content {
          resource_link = gke_cluster.value["resource_link"]
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
output "id" {
  description = "returns a string"
  value       = google_gke_hub_membership.this.id
}

output "name" {
  description = "returns a string"
  value       = google_gke_hub_membership.this.name
}

output "project" {
  description = "returns a string"
  value       = google_gke_hub_membership.this.project
}

output "this" {
  value = google_gke_hub_membership.this
}
```

[top](#index)