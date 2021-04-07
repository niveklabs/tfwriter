# google_access_context_manager_gcp_user_access_binding

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
module "google_access_context_manager_gcp_user_access_binding" {
  source = "./modules/google/r/google_access_context_manager_gcp_user_access_binding"

  # access_levels - (required) is a type of list of string
  access_levels = []
  # group_key - (required) is a type of string
  group_key = null
  # organization_id - (required) is a type of string
  organization_id = null

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
variable "access_levels" {
  description = "(required) - Required. Access level that a user must have to be granted access. Only one access level is supported, not multiple. This repeated field must have exactly one element. Example: \"accessPolicies/9522/accessLevels/device_trusted\""
  type        = list(string)
}

variable "group_key" {
  description = "(required) - Required. Immutable. Google Group id whose members are subject to this binding's restrictions. See \"id\" in the G Suite Directory API's Groups resource. If a group's email address/alias is changed, this resource will continue to point at the changed group. This field does not accept group email addresses or aliases. Example: \"01d520gv4vjcrht\""
  type        = string
}

variable "organization_id" {
  description = "(required) - Required. ID of the parent organization."
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
resource "google_access_context_manager_gcp_user_access_binding" "this" {
  # access_levels - (required) is a type of list of string
  access_levels = var.access_levels
  # group_key - (required) is a type of string
  group_key = var.group_key
  # organization_id - (required) is a type of string
  organization_id = var.organization_id

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
  value       = google_access_context_manager_gcp_user_access_binding.this.id
}

output "name" {
  description = "returns a string"
  value       = google_access_context_manager_gcp_user_access_binding.this.name
}

output "this" {
  value = google_access_context_manager_gcp_user_access_binding.this
}
```

[top](#index)