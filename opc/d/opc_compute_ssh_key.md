# opc_compute_ssh_key

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_ssh_key" {
  source = "./modules/opc/d/opc_compute_ssh_key"

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
data "opc_compute_ssh_key" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.opc_compute_ssh_key.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_ssh_key.this.id
}

output "key" {
  description = "returns a string"
  value       = data.opc_compute_ssh_key.this.key
}

output "this" {
  value = opc_compute_ssh_key.this
}
```

[top](#index)