# okta_auth_server_scope

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_auth_server_scope" {
  source = "./modules/okta/r/okta_auth_server_scope"

  # auth_server_id - (required) is a type of string
  auth_server_id = null
  # consent - (optional) is a type of string
  consent = null
  # default - (optional) is a type of bool
  default = null
  # description - (optional) is a type of string
  description = null
  # metadata_publish - (optional) is a type of string
  metadata_publish = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_server_id" {
  description = "(required) - Auth server ID"
  type        = string
}

variable "consent" {
  description = "(optional) - EA Feature and thus it is simply ignored if the feature is off"
  type        = string
  default     = null
}

variable "default" {
  description = "(optional) - A default scope will be returned in an access token when the client omits the scope parameter in a token request, provided this scope is allowed as part of the access policy rule."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata_publish" {
  description = "(optional) - Whether to publish metadata or not, matching API type despite the fact it could just be a boolean"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Auth server scope name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_scope" "this" {
  auth_server_id   = var.auth_server_id
  consent          = var.consent
  default          = var.default
  description      = var.description
  metadata_publish = var.metadata_publish
  name             = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_auth_server_scope.this.id
}

output "this" {
  value = okta_auth_server_scope.this
}
```

[top](#index)