# okta_app_oauth_redirect_uri

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
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app_oauth_redirect_uri" {
  source = "./modules/okta/r/okta_app_oauth_redirect_uri"

  # app_id - (required) is a type of string
  app_id = null
  # uri - (required) is a type of string
  uri = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "uri" {
  description = "(required) - Redirect URI to append to Okta OIDC application."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_app_oauth_redirect_uri" "this" {
  # app_id - (required) is a type of string
  app_id = var.app_id
  # uri - (required) is a type of string
  uri = var.uri
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_app_oauth_redirect_uri.this.id
}

output "this" {
  value = okta_app_oauth_redirect_uri.this
}
```

[top](#index)