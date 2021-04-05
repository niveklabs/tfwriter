# google_identity_platform_tenant_oauth_idp_config

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
module "google_identity_platform_tenant_oauth_idp_config" {
  source = "./modules/google/r/google_identity_platform_tenant_oauth_idp_config"

  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # issuer - (required) is a type of string
  issuer = null
  # name - (required) is a type of string
  name = null
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
  description = "(required) - The client id of an OAuth client."
  type        = string
}

variable "client_secret" {
  description = "(optional) - The client secret of the OAuth client, to enable OIDC code flow."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Human friendly display name."
  type        = string
}

variable "enabled" {
  description = "(optional) - If this config allows users to sign in with the provider."
  type        = bool
  default     = null
}

variable "issuer" {
  description = "(required) - For OIDC Idps, the issuer identifier."
  type        = string
}

variable "name" {
  description = "(required) - The name of the OauthIdpConfig. Must start with 'oidc.'."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant" {
  description = "(required) - The name of the tenant where this OIDC IDP configuration resource exists"
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
resource "google_identity_platform_tenant_oauth_idp_config" "this" {
  client_id     = var.client_id
  client_secret = var.client_secret
  display_name  = var.display_name
  enabled       = var.enabled
  issuer        = var.issuer
  name          = var.name
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
  value       = google_identity_platform_tenant_oauth_idp_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_identity_platform_tenant_oauth_idp_config.this.project
}

output "this" {
  value = google_identity_platform_tenant_oauth_idp_config.this
}
```

[top](#index)