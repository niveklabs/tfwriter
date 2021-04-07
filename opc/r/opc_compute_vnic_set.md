# opc_compute_vnic_set

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
module "opc_compute_vnic_set" {
  source = "./modules/opc/r/opc_compute_vnic_set"

  # applied_acls - (optional) is a type of list of string
  applied_acls = []
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
  # virtual_nics - (optional) is a type of list of string
  virtual_nics = []
}
```

[top](#index)

### Variables

```terraform
variable "applied_acls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "virtual_nics" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_vnic_set" "this" {
  # applied_acls - (optional) is a type of list of string
  applied_acls = var.applied_acls
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of list of string
  tags = var.tags
  # virtual_nics - (optional) is a type of list of string
  virtual_nics = var.virtual_nics
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_vnic_set.this.id
}

output "virtual_nics" {
  description = "returns a list of string"
  value       = opc_compute_vnic_set.this.virtual_nics
}

output "this" {
  value = opc_compute_vnic_set.this
}
```

[top](#index)