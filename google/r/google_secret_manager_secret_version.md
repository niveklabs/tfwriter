# google_secret_manager_secret_version

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
module "google_secret_manager_secret_version" {
  source = "./modules/google/r/google_secret_manager_secret_version"

  # enabled - (optional) is a type of bool
  enabled = null
  # secret - (required) is a type of string
  secret = null
  # secret_data - (required) is a type of string
  secret_data = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - The current state of the SecretVersion."
  type        = bool
  default     = null
}

variable "secret" {
  description = "(required) - Secret Manager secret resource"
  type        = string
}

variable "secret_data" {
  description = "(required) - The secret data. Must be no larger than 64KiB."
  type        = string
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
resource "google_secret_manager_secret_version" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # secret - (required) is a type of string
  secret = var.secret
  # secret_data - (required) is a type of string
  secret_data = var.secret_data

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
output "create_time" {
  description = "returns a string"
  value       = google_secret_manager_secret_version.this.create_time
}

output "destroy_time" {
  description = "returns a string"
  value       = google_secret_manager_secret_version.this.destroy_time
}

output "id" {
  description = "returns a string"
  value       = google_secret_manager_secret_version.this.id
}

output "name" {
  description = "returns a string"
  value       = google_secret_manager_secret_version.this.name
}

output "this" {
  value = google_secret_manager_secret_version.this
}
```

[top](#index)