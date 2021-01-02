# google_compute_target_pool

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_target_pool" {
  source = "./modules/google/r/google_compute_target_pool"

  # backup_pool - (optional) is a type of string
  backup_pool = null
  # description - (optional) is a type of string
  description = null
  # failover_ratio - (optional) is a type of number
  failover_ratio = null
  # health_checks - (optional) is a type of list of string
  health_checks = []
  # instances - (optional) is a type of set of string
  instances = []
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # session_affinity - (optional) is a type of string
  session_affinity = null

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
variable "backup_pool" {
  description = "(optional) - URL to the backup target pool. Must also set failover_ratio."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Textual description field."
  type        = string
  default     = null
}

variable "failover_ratio" {
  description = "(optional) - Ratio (0 to 1) of failed nodes before using the backup pool (which must also be set)."
  type        = number
  default     = null
}

variable "health_checks" {
  description = "(optional) - List of zero or one health check name or self_link. Only legacy google_compute_http_health_check is supported."
  type        = list(string)
  default     = null
}

variable "instances" {
  description = "(optional) - List of instances in the pool. They can be given as URLs, or in the form of \"zone/name\". Note that the instances need not exist at the time of target pool creation, so there is no need to use the Terraform interpolators to create a dependency on the instances from the target pool."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the resource, required by GCE. Changing this forces a new resource to be created."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Where the target pool resides. Defaults to project region."
  type        = string
  default     = null
}

variable "session_affinity" {
  description = "(optional) - How to distribute load. Options are \"NONE\" (no affinity). \"CLIENT_IP\" (hash of the source/dest addresses / ports), and \"CLIENT_IP_PROTO\" also includes the protocol (default \"NONE\")."
  type        = string
  default     = null
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

```terraform
resource "google_compute_target_pool" "this" {
  backup_pool      = var.backup_pool
  description      = var.description
  failover_ratio   = var.failover_ratio
  health_checks    = var.health_checks
  instances        = var.instances
  name             = var.name
  project          = var.project
  region           = var.region
  session_affinity = var.session_affinity

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
  value       = google_compute_target_pool.this.id
}

output "instances" {
  description = "returns a set of string"
  value       = google_compute_target_pool.this.instances
}

output "project" {
  description = "returns a string"
  value       = google_compute_target_pool.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_target_pool.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_target_pool.this.self_link
}

output "this" {
  value = google_compute_target_pool.this
}
```

[top](#index)