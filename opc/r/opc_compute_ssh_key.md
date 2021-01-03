# opc_compute_ssh_key

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/opc/r/opc_compute_ssh_key"

  # enabled - (optional) is a type of bool
  enabled = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
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
resource "opc_compute_ssh_key" "this" {
  enabled = var.enabled
  key     = var.key
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ssh_key.this.id
}

output "this" {
  value = opc_compute_ssh_key.this
}
```

[top](#index)