# opc_compute_image_list

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
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_image_list" {
  source = "./modules/opc/r/opc_compute_image_list"

  # default - (optional) is a type of number
  default = null
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "default" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
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
resource "opc_compute_image_list" "this" {
  default     = var.default
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_image_list.this.id
}

output "this" {
  value = opc_compute_image_list.this
}
```

[top](#index)