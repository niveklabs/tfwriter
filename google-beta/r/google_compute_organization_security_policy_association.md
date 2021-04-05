# google_compute_organization_security_policy_association

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
module "google_compute_organization_security_policy_association" {
  source = "./modules/google-beta/r/google_compute_organization_security_policy_association"

  # attachment_id - (required) is a type of string
  attachment_id = null
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of string
  policy_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attachment_id" {
  description = "(required) - The resource that the security policy is attached to."
  type        = string
}

variable "name" {
  description = "(required) - The name for an association."
  type        = string
}

variable "policy_id" {
  description = "(required) - The security policy ID of the association."
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
resource "google_compute_organization_security_policy_association" "this" {
  attachment_id = var.attachment_id
  name          = var.name
  policy_id     = var.policy_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = google_compute_organization_security_policy_association.this.display_name
}

output "id" {
  description = "returns a string"
  value       = google_compute_organization_security_policy_association.this.id
}

output "this" {
  value = google_compute_organization_security_policy_association.this
}
```

[top](#index)