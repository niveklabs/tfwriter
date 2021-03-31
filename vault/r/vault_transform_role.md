# vault_transform_role

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_transform_role" {
  source = "./modules/vault/r/vault_transform_role"

  # name - (required) is a type of string
  name = null
  # path - (required) is a type of string
  path = null
  # transformations - (optional) is a type of list of string
  transformations = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the role."
  type        = string
}

variable "path" {
  description = "(required) - The mount path for a back-end, for example, the path given in \"$ vault auth enable -path=my-aws aws\"."
  type        = string
}

variable "transformations" {
  description = "(optional) - A comma separated string or slice of transformations to use."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_transform_role" "this" {
  name            = var.name
  path            = var.path
  transformations = var.transformations
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_transform_role.this.id
}

output "this" {
  value = vault_transform_role.this
}
```

[top](#index)