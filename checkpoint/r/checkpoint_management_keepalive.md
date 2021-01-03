# checkpoint_management_keepalive

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_keepalive" {
  source = "./modules/checkpoint/r/checkpoint_management_keepalive"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_keepalive" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_keepalive.this.id
}

output "this" {
  value = checkpoint_management_keepalive.this
}
```

[top](#index)