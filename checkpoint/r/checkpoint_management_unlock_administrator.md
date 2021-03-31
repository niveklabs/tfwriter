# checkpoint_management_unlock_administrator

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_unlock_administrator" {
  source = "./modules/checkpoint/r/checkpoint_management_unlock_administrator"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Object name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_unlock_administrator" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_unlock_administrator.this.id
}

output "this" {
  value = checkpoint_management_unlock_administrator.this
}
```

[top](#index)