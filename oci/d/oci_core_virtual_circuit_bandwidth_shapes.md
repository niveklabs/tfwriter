# oci_core_virtual_circuit_bandwidth_shapes

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_virtual_circuit_bandwidth_shapes" {
  source = "./modules/oci/d/oci_core_virtual_circuit_bandwidth_shapes"

  # provider_service_id - (required) is a type of string
  provider_service_id = null

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
variable "provider_service_id" {
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
data "oci_core_virtual_circuit_bandwidth_shapes" "this" {
  provider_service_id = var.provider_service_id

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
  value       = data.oci_core_virtual_circuit_bandwidth_shapes.this.id
}

output "virtual_circuit_bandwidth_shapes" {
  description = "returns a list of object"
  value       = data.oci_core_virtual_circuit_bandwidth_shapes.this.virtual_circuit_bandwidth_shapes
}

output "this" {
  value = oci_core_virtual_circuit_bandwidth_shapes.this
}
```

[top](#index)