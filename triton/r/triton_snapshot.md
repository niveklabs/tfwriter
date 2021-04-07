# triton_snapshot

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_snapshot" {
  source = "./modules/triton/r/triton_snapshot"

  # machine_id - (required) is a type of string
  machine_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "machine_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "triton_snapshot" "this" {
  # machine_id - (required) is a type of string
  machine_id = var.machine_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = triton_snapshot.this.id
}

output "state" {
  description = "returns a string"
  value       = triton_snapshot.this.state
}

output "this" {
  value = triton_snapshot.this
}
```

[top](#index)