# okta_app_oauth_api_scope

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
module "okta_app_oauth_api_scope" {
  source = "./modules/okta/r/okta_app_oauth_api_scope"

  # app_id - (required) is a type of string
  app_id = null
  # issuer - (required) is a type of string
  issuer = null
  # scopes - (required) is a type of list of string
  scopes = []
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required) - ID of the application."
  type        = string
}

variable "issuer" {
  description = "(required) - The issuer of your Org Authorization Server, your Org URL."
  type        = string
}

variable "scopes" {
  description = "(required) - Scopes of the application for which consent is granted."
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "okta_app_oauth_api_scope" "this" {
  # app_id - (required) is a type of string
  app_id = var.app_id
  # issuer - (required) is a type of string
  issuer = var.issuer
  # scopes - (required) is a type of list of string
  scopes = var.scopes
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_app_oauth_api_scope.this.id
}

output "this" {
  value = okta_app_oauth_api_scope.this
}
```

[top](#index)