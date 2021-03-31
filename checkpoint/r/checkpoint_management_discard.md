# checkpoint_management_discard

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
module "checkpoint_management_discard" {
  source = "./modules/checkpoint/r/checkpoint_management_discard"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_discard" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_discard.this.id
}

output "this" {
  value = checkpoint_management_discard.this
}
```

[top](#index)