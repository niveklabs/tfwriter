# google_compute_organization_security_policy

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
module "google_compute_organization_security_policy" {
  source = "./modules/google-beta/r/google_compute_organization_security_policy"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null
  # type - (optional) is a type of string
  type = null

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
  description = "(optional) - A textual description for the organization security policy."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - A textual name of the security policy."
  type        = string
}

variable "parent" {
  description = "(required) - The parent of this OrganizationSecurityPolicy in the Cloud Resource Hierarchy.\nFormat: organizations/{organization_id} or folders/{folder_id}"
  type        = string
}

variable "type" {
  description = "(optional) - The type indicates the intended use of the security policy.\nFor organization security policies, the only supported type\nis \"FIREWALL\". Default value: \"FIREWALL\" Possible values: [\"FIREWALL\"]"
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
resource "google_compute_organization_security_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # parent - (required) is a type of string
  parent = var.parent
  # type - (optional) is a type of string
  type = var.type

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
output "fingerprint" {
  description = "returns a string"
  value       = google_compute_organization_security_policy.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_organization_security_policy.this.id
}

output "policy_id" {
  description = "returns a string"
  value       = google_compute_organization_security_policy.this.policy_id
}

output "this" {
  value = google_compute_organization_security_policy.this
}
```

[top](#index)