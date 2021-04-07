# google_service_account

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
module "google_service_account" {
  source = "./modules/google/r/google_service_account"

  # account_id - (required) is a type of string
  account_id = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
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
variable "account_id" {
  description = "(required) - The account id that is used to generate the service account email address and a stable unique id. It is unique within a project, must be 6-30 characters long, and match the regular expression [a-z]([-a-z0-9]*[a-z0-9]) to comply with RFC1035. Changing this forces a new service account to be created."
  type        = string
}

variable "description" {
  description = "(optional) - A text description of the service account. Must be less than or equal to 256 UTF-8 bytes."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name for the service account. Can be updated without creating a new resource."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project that the service account will be created in. Defaults to the provider project configuration."
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
resource "google_service_account" "this" {
  # account_id - (required) is a type of string
  account_id = var.account_id
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # project - (optional) is a type of string
  project = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = google_service_account.this.email
}

output "id" {
  description = "returns a string"
  value       = google_service_account.this.id
}

output "name" {
  description = "returns a string"
  value       = google_service_account.this.name
}

output "project" {
  description = "returns a string"
  value       = google_service_account.this.project
}

output "unique_id" {
  description = "returns a string"
  value       = google_service_account.this.unique_id
}

output "this" {
  value = google_service_account.this
}
```

[top](#index)