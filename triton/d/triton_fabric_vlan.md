# triton_fabric_vlan

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
module "triton_fabric_vlan" {
  source = "./modules/triton/d/triton_fabric_vlan"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "triton_fabric_vlan" "this" {
  description = var.description
  name        = var.name
  vlan_id     = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.triton_fabric_vlan.this.id
}

output "this" {
  value = triton_fabric_vlan.this
}
```

[top](#index)