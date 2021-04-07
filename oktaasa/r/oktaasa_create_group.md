# oktaasa_create_group

[back](../oktaasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oktaasa = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oktaasa_create_group" {
  source = "./modules/oktaasa/r/oktaasa_create_group"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "oktaasa_create_group" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oktaasa_create_group.this.id
}

output "this" {
  value = oktaasa_create_group.this
}
```

[top](#index)