# opc_compute_acl

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
module "opc_compute_acl" {
  source = "./modules/opc/r/opc_compute_acl"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
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

variable "enabled" {
  description = "(optional)"
  type        = bool
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
```

[top](#index)

### Resource

```terraform
resource "opc_compute_acl" "this" {
  description = var.description
  enabled     = var.enabled
  name        = var.name
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_acl.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_acl.this.uri
}

output "this" {
  value = opc_compute_acl.this
}
```

[top](#index)