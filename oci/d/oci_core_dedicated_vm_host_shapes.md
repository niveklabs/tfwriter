# oci_core_dedicated_vm_host_shapes

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
module "oci_core_dedicated_vm_host_shapes" {
  source = "./modules/oci/d/oci_core_dedicated_vm_host_shapes"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # instance_shape_name - (optional) is a type of string
  instance_shape_name = null

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

variable "instance_shape_name" {
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
data "oci_core_dedicated_vm_host_shapes" "this" {
  # availability_domain - (optional) is a type of string
  availability_domain = var.availability_domain
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # instance_shape_name - (optional) is a type of string
  instance_shape_name = var.instance_shape_name

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
output "dedicated_vm_host_shapes" {
  description = "returns a list of object"
  value       = data.oci_core_dedicated_vm_host_shapes.this.dedicated_vm_host_shapes
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_dedicated_vm_host_shapes.this.id
}

output "this" {
  value = oci_core_dedicated_vm_host_shapes.this
}
```

[top](#index)