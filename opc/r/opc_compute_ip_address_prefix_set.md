# opc_compute_ip_address_prefix_set

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
module "opc_compute_ip_address_prefix_set" {
  source = "./modules/opc/r/opc_compute_ip_address_prefix_set"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # prefixes - (optional) is a type of list of string
  prefixes = []
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "prefixes" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
resource "opc_compute_ip_address_prefix_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # prefixes - (optional) is a type of list of string
  prefixes = var.prefixes
  # tags - (optional) is a type of list of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_address_prefix_set.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_ip_address_prefix_set.this.uri
}

output "this" {
  value = opc_compute_ip_address_prefix_set.this
}
```

[top](#index)