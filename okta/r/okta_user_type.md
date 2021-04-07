# okta_user_type

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
module "okta_user_type" {
  source = "./modules/okta/r/okta_user_type"

  # description - (required) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - A human-readable description of the type"
  type        = string
}

variable "display_name" {
  description = "(required) - The display name for the type\t"
  type        = string
}

variable "name" {
  description = "(required) - The display name for the type"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_user_type" "this" {
  # description - (required) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_user_type.this.id
}

output "this" {
  value = okta_user_type.this
}
```

[top](#index)