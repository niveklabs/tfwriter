# google_iam_workload_identity_pool

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
module "google_iam_workload_identity_pool" {
  source = "./modules/google-beta/r/google_iam_workload_identity_pool"

  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # display_name - (optional) is a type of string
  display_name = null
  # project - (optional) is a type of string
  project = null
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = null

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
  description = "(optional) - A description of the pool. Cannot exceed 256 characters."
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional) - Whether the pool is disabled. You cannot use a disabled pool to exchange tokens, or use\nexisting tokens to access resources. If the pool is re-enabled, existing tokens grant\naccess again."
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional) - A display name for the pool. Cannot exceed 32 characters."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workload_identity_pool_id" {
  description = "(required) - The ID to use for the pool, which becomes the final component of the resource name. This\nvalue should be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
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
resource "google_iam_workload_identity_pool" "this" {
  # description - (optional) is a type of string
  description = var.description
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # project - (optional) is a type of string
  project = var.project
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = var.workload_identity_pool_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = google_iam_workload_identity_pool.this.id
}

output "name" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool.this.name
}

output "project" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool.this.project
}

output "state" {
  description = "returns a string"
  value       = google_iam_workload_identity_pool.this.state
}

output "this" {
  value = google_iam_workload_identity_pool.this
}
```

[top](#index)