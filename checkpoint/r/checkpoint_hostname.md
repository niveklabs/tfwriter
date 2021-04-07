# checkpoint_hostname

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
module "checkpoint_hostname" {
  source = "./modules/checkpoint/r/checkpoint_hostname"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - interface name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_hostname" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_hostname.this.id
}

output "this" {
  value = checkpoint_hostname.this
}
```

[top](#index)