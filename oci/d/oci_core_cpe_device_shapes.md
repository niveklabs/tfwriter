# oci_core_cpe_device_shapes

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
module "oci_core_cpe_device_shapes" {
  source = "./modules/oci/d/oci_core_cpe_device_shapes"


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
data "oci_core_cpe_device_shapes" "this" {

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
output "cpe_device_shapes" {
  description = "returns a list of object"
  value       = data.oci_core_cpe_device_shapes.this.cpe_device_shapes
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cpe_device_shapes.this.id
}

output "this" {
  value = oci_core_cpe_device_shapes.this
}
```

[top](#index)