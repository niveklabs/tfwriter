# checkpoint_management_logout

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
module "checkpoint_management_logout" {
  source = "./modules/checkpoint/r/checkpoint_management_logout"

  # triggers - (optional) is a type of set of string
  triggers = []
}
```

[top](#index)

### Variables

```terraform
variable "triggers" {
  description = "(optional) - Triggers a logout if there are any changes to objects in this list."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_logout" "this" {
  # triggers - (optional) is a type of set of string
  triggers = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_logout.this.id
}

output "this" {
  value = checkpoint_management_logout.this
}
```

[top](#index)