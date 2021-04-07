# nutanix_user

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_user" {
  source = "./modules/nutanix/r/nutanix_user"

  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}

  categories = [{
    name  = null
    value = null
  }]

  directory_service_user = [{
    default_user_principal_name = null
    directory_service_reference = [{
      kind = null
      name = null
      uuid = null
    }]
    user_principal_name = null
  }]

  identity_provider_user = [{
    identity_provider_reference = [{
      kind = null
      name = null
      uuid = null
    }]
    username = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "directory_service_user" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_user_principal_name = string
      directory_service_reference = list(object(
        {
          kind = string
          name = string
          uuid = string
        }
      ))
      user_principal_name = string
    }
  ))
  default = []
}

variable "identity_provider_user" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_provider_reference = list(object(
        {
          kind = string
          name = string
          uuid = string
        }
      ))
      username = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_user" "this" {
  # owner_reference - (optional) is a type of map of string
  owner_reference = var.owner_reference
  # project_reference - (optional) is a type of map of string
  project_reference = var.project_reference

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

  dynamic "directory_service_user" {
    for_each = var.directory_service_user
    content {
      # user_principal_name - (optional) is a type of string
      user_principal_name = directory_service_user.value["user_principal_name"]

      dynamic "directory_service_reference" {
        for_each = directory_service_user.value.directory_service_reference
        content {
          # kind - (optional) is a type of string
          kind = directory_service_reference.value["kind"]
          # name - (optional) is a type of string
          name = directory_service_reference.value["name"]
          # uuid - (required) is a type of string
          uuid = directory_service_reference.value["uuid"]
        }
      }

    }
  }

  dynamic "identity_provider_user" {
    for_each = var.identity_provider_user
    content {
      # username - (optional) is a type of string
      username = identity_provider_user.value["username"]

      dynamic "identity_provider_reference" {
        for_each = identity_provider_user.value.identity_provider_reference
        content {
          # kind - (optional) is a type of string
          kind = identity_provider_reference.value["kind"]
          # name - (optional) is a type of string
          name = identity_provider_reference.value["name"]
          # uuid - (required) is a type of string
          uuid = identity_provider_reference.value["uuid"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_control_policy_reference_list" {
  description = "returns a set of object"
  value       = nutanix_user.this.access_control_policy_reference_list
}

output "api_version" {
  description = "returns a string"
  value       = nutanix_user.this.api_version
}

output "display_name" {
  description = "returns a string"
  value       = nutanix_user.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nutanix_user.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_user.this.metadata
}

output "name" {
  description = "returns a string"
  value       = nutanix_user.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_user.this.owner_reference
}

output "project_reference_list" {
  description = "returns a set of object"
  value       = nutanix_user.this.project_reference_list
}

output "state" {
  description = "returns a string"
  value       = nutanix_user.this.state
}

output "user_type" {
  description = "returns a string"
  value       = nutanix_user.this.user_type
}

output "this" {
  value = nutanix_user.this
}
```

[top](#index)