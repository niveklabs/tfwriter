# google_identity_platform_tenant

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_identity_platform_tenant" {
  source = "./modules/google/r/google_identity_platform_tenant"

  # allow_password_signup - (optional) is a type of bool
  allow_password_signup = null
  # disable_auth - (optional) is a type of bool
  disable_auth = null
  # display_name - (required) is a type of string
  display_name = null
  # enable_email_link_signin - (optional) is a type of bool
  enable_email_link_signin = null
  # project - (optional) is a type of string
  project = null

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
variable "allow_password_signup" {
  description = "(optional) - Whether to allow email/password user authentication."
  type        = bool
  default     = null
}

variable "disable_auth" {
  description = "(optional) - Whether authentication is disabled for the tenant. If true, the users under\nthe disabled tenant are not allowed to sign-in. Admins of the disabled tenant\nare not able to manage its users."
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(required) - Human friendly display name of the tenant."
  type        = string
}

variable "enable_email_link_signin" {
  description = "(optional) - Whether to enable email link user authentication."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
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
resource "google_identity_platform_tenant" "this" {
  allow_password_signup    = var.allow_password_signup
  disable_auth             = var.disable_auth
  display_name             = var.display_name
  enable_email_link_signin = var.enable_email_link_signin
  project                  = var.project

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
  value       = google_identity_platform_tenant.this.id
}

output "name" {
  description = "returns a string"
  value       = google_identity_platform_tenant.this.name
}

output "project" {
  description = "returns a string"
  value       = google_identity_platform_tenant.this.project
}

output "this" {
  value = google_identity_platform_tenant.this
}
```

[top](#index)