# checkpoint_management_disconnect

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
module "checkpoint_management_disconnect" {
  source = "./modules/checkpoint/r/checkpoint_management_disconnect"

  # discard - (optional) is a type of bool
  discard = null
}
```

[top](#index)

### Variables

```terraform
variable "discard" {
  description = "(optional) - Discard all changes committed during the session."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_disconnect" "this" {
  # discard - (optional) is a type of bool
  discard = var.discard
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_disconnect.this.id
}

output "this" {
  value = checkpoint_management_disconnect.this
}
```

[top](#index)