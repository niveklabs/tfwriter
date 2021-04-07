# okta_auth_server_scopes

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "okta_auth_server_scopes" {
  source = "./modules/okta/d/okta_auth_server_scopes"

  # auth_server_id - (required) is a type of string
  auth_server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_server_id" {
  description = "(required) - Auth server ID"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "okta_auth_server_scopes" "this" {
  # auth_server_id - (required) is a type of string
  auth_server_id = var.auth_server_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_auth_server_scopes.this.id
}

output "scopes" {
  description = "returns a list of object"
  value       = data.okta_auth_server_scopes.this.scopes
}

output "this" {
  value = okta_auth_server_scopes.this
}
```

[top](#index)