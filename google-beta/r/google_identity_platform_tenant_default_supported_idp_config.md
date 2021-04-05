# google_identity_platform_tenant_default_supported_idp_config

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
module "google_identity_platform_tenant_default_supported_idp_config" {
  source = "./modules/google-beta/r/google_identity_platform_tenant_default_supported_idp_config"

  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # enabled - (optional) is a type of bool
  enabled = null
  # idp_id - (required) is a type of string
  idp_id = null
  # project - (optional) is a type of string
  project = null
  # tenant - (required) is a type of string
  tenant = null

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
variable "client_id" {
  description = "(required) - OAuth client ID"
  type        = string
}

variable "client_secret" {
  description = "(required) - OAuth client secret"
  type        = string
}

variable "enabled" {
  description = "(optional) - If this IDP allows the user to sign in"
  type        = bool
  default     = null
}

variable "idp_id" {
  description = "(required) - ID of the IDP. Possible values include:\n\n* 'apple.com'\n\n* 'facebook.com'\n\n* 'gc.apple.com'\n\n* 'github.com'\n\n* 'google.com'\n\n* 'linkedin.com'\n\n* 'microsoft.com'\n\n* 'playgames.google.com'\n\n* 'twitter.com'\n\n* 'yahoo.com'"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant" {
  description = "(required) - The name of the tenant where this DefaultSupportedIdpConfig resource exists"
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
resource "google_identity_platform_tenant_default_supported_idp_config" "this" {
  client_id     = var.client_id
  client_secret = var.client_secret
  enabled       = var.enabled
  idp_id        = var.idp_id
  project       = var.project
  tenant        = var.tenant

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
  value       = google_identity_platform_tenant_default_supported_idp_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_identity_platform_tenant_default_supported_idp_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_identity_platform_tenant_default_supported_idp_config.this.project
}

output "this" {
  value = google_identity_platform_tenant_default_supported_idp_config.this
}
```

[top](#index)