# oci_core_virtual_circuit_public_prefixes

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_virtual_circuit_public_prefixes" {
  source = "./modules/oci/d/oci_core_virtual_circuit_public_prefixes"

  # verification_state - (optional) is a type of string
  verification_state = null
  # virtual_circuit_id - (required) is a type of string
  virtual_circuit_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "verification_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_circuit_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_virtual_circuit_public_prefixes" "this" {
  verification_state = var.verification_state
  virtual_circuit_id = var.virtual_circuit_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_virtual_circuit_public_prefixes.this.id
}

output "virtual_circuit_public_prefixes" {
  description = "returns a list of object"
  value       = data.oci_core_virtual_circuit_public_prefixes.this.virtual_circuit_public_prefixes
}

output "this" {
  value = oci_core_virtual_circuit_public_prefixes.this
}
```

[top](#index)