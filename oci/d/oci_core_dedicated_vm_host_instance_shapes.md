# oci_core_dedicated_vm_host_instance_shapes

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
module "oci_core_dedicated_vm_host_instance_shapes" {
  source = "./modules/oci/d/oci_core_dedicated_vm_host_instance_shapes"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # dedicated_vm_host_shape - (optional) is a type of string
  dedicated_vm_host_shape = null

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
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "dedicated_vm_host_shape" {
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
data "oci_core_dedicated_vm_host_instance_shapes" "this" {
  # availability_domain - (optional) is a type of string
  availability_domain = var.availability_domain
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # dedicated_vm_host_shape - (optional) is a type of string
  dedicated_vm_host_shape = var.dedicated_vm_host_shape

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
output "dedicated_vm_host_instance_shapes" {
  description = "returns a list of object"
  value       = data.oci_core_dedicated_vm_host_instance_shapes.this.dedicated_vm_host_instance_shapes
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_dedicated_vm_host_instance_shapes.this.id
}

output "this" {
  value = oci_core_dedicated_vm_host_instance_shapes.this
}
```

[top](#index)