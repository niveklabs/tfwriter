# google_storage_hmac_key

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
module "google_storage_hmac_key" {
  source = "./modules/google-beta/r/google_storage_hmac_key"

  # project - (optional) is a type of string
  project = null
  # service_account_email - (required) is a type of string
  service_account_email = null
  # state - (optional) is a type of string
  state = null

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
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_account_email" {
  description = "(required) - The email address of the key's associated service account."
  type        = string
}

variable "state" {
  description = "(optional) - The state of the key. Can be set to one of ACTIVE, INACTIVE. Default value: \"ACTIVE\" Possible values: [\"ACTIVE\", \"INACTIVE\"]"
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
resource "google_storage_hmac_key" "this" {
  project               = var.project
  service_account_email = var.service_account_email
  state                 = var.state

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
output "access_id" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.access_id
}

output "id" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.id
}

output "project" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.project
}

output "secret" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.secret
  sensitive   = true
}

output "time_created" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.time_created
}

output "updated" {
  description = "returns a string"
  value       = google_storage_hmac_key.this.updated
}

output "this" {
  value = google_storage_hmac_key.this
}
```

[top](#index)