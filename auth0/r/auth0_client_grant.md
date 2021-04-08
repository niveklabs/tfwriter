# auth0_client_grant

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_client_grant" {
  source = "./modules/auth0/r/auth0_client_grant"

  # audience - (required) is a type of string
  audience = null
  # client_id - (required) is a type of string
  client_id = null
  # scope - (required) is a type of list of string
  scope = []
}
```

[top](#index)

### Variables

```terraform
variable "audience" {
  description = "(required)"
  type        = string
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "auth0_client_grant" "this" {
  # audience - (required) is a type of string
  audience = var.audience
  # client_id - (required) is a type of string
  client_id = var.client_id
  # scope - (required) is a type of list of string
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_client_grant.this.id
}

output "this" {
  value = auth0_client_grant.this
}
```

[top](#index)