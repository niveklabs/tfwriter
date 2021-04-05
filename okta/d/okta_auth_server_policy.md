# okta_auth_server_policy

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
module "okta_auth_server_policy" {
  source = "./modules/okta/d/okta_auth_server_policy"

  # auth_server_id - (required) is a type of string
  auth_server_id = null
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

variable "name" {
  description = "(required) - Name of the policy"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "okta_auth_server_policy" "this" {
  auth_server_id = var.auth_server_id
  name           = var.name
}
```

[top](#index)

### Outputs

```terraform
output "assigned_clients" {
  description = "returns a set of string"
  value       = data.okta_auth_server_policy.this.assigned_clients
}

output "description" {
  description = "returns a string"
  value       = data.okta_auth_server_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.okta_auth_server_policy.this.id
}

output "this" {
  value = okta_auth_server_policy.this
}
```

[top](#index)