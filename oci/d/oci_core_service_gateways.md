# oci_core_service_gateways

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_service_gateways" {
  source = "./modules/oci/d/oci_core_service_gateways"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # state - (optional) is a type of string
  state = null
  # vcn_id - (optional) is a type of string
  vcn_id = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcn_id" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_core_service_gateways" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # state - (optional) is a type of string
  state = var.state
  # vcn_id - (optional) is a type of string
  vcn_id = var.vcn_id

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
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
  value       = data.oci_core_service_gateways.this.id
}

output "service_gateways" {
  description = "returns a list of object"
  value       = data.oci_core_service_gateways.this.service_gateways
}

output "this" {
  value = oci_core_service_gateways.this
}
```

[top](#index)