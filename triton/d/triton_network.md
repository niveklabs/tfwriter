# triton_network

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "triton_network" {
  source = "./modules/triton/d/triton_network"

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

### Datasource

```terraform
data "triton_network" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fabric" {
  description = "returns a bool"
  value       = data.triton_network.this.fabric
}

output "id" {
  description = "returns a string"
  value       = data.triton_network.this.id
}

output "public" {
  description = "returns a bool"
  value       = data.triton_network.this.public
}

output "this" {
  value = triton_network.this
}
```

[top](#index)