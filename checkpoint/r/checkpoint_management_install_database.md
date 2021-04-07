# checkpoint_management_install_database

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
module "checkpoint_management_install_database" {
  source = "./modules/checkpoint/r/checkpoint_management_install_database"

  # targets - (required) is a type of set of string
  targets = []
}
```

[top](#index)

### Variables

```terraform
variable "targets" {
  description = "(required) - Check Point host(s) with one or more Management Software Blades enabled. The targets can be identified by their name or unique identifier."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_install_database" "this" {
  # targets - (required) is a type of set of string
  targets = var.targets
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_install_database.this.id
}

output "tasks" {
  description = "returns a set of string"
  value       = checkpoint_management_install_database.this.tasks
}

output "this" {
  value = checkpoint_management_install_database.this
}
```

[top](#index)