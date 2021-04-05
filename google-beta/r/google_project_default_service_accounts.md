# google_project_default_service_accounts

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
module "google_project_default_service_accounts" {
  source = "./modules/google-beta/r/google_project_default_service_accounts"

  # action - (required) is a type of string
  action = null
  # project - (required) is a type of string
  project = null
  # restore_policy - (optional) is a type of string
  restore_policy = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required) - The action to be performed in the default service accounts. Valid values are: DEPRIVILEGE, DELETE, DISABLE.\n\t\t\t\tNote that DEPRIVILEGE action will ignore the REVERT configuration in the restore_policy."
  type        = string
}

variable "project" {
  description = "(required) - The project ID where service accounts are created."
  type        = string
}

variable "restore_policy" {
  description = "(optional) - The action to be performed in the default service accounts on the resource destroy.\n\t\t\t\tValid values are NONE, REVERT and REVERT_AND_IGNORE_FAILURE. It is applied for any action but in the DEPRIVILEGE."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_project_default_service_accounts" "this" {
  action         = var.action
  project        = var.project
  restore_policy = var.restore_policy

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_project_default_service_accounts.this.id
}

output "service_accounts" {
  description = "returns a map of string"
  value       = google_project_default_service_accounts.this.service_accounts
}

output "this" {
  value = google_project_default_service_accounts.this
}
```

[top](#index)