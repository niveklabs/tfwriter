# oci_core_cpe_device_shape

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
module "oci_core_cpe_device_shape" {
  source = "./modules/oci/d/oci_core_cpe_device_shape"

  # cpe_device_shape_id - (required) is a type of string
  cpe_device_shape_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cpe_device_shape_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_cpe_device_shape" "this" {
  cpe_device_shape_id = var.cpe_device_shape_id
}
```

[top](#index)

### Outputs

```terraform
output "cpe_device_info" {
  description = "returns a list of object"
  value       = data.oci_core_cpe_device_shape.this.cpe_device_info
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_cpe_device_shape.this.id
}

output "parameters" {
  description = "returns a list of object"
  value       = data.oci_core_cpe_device_shape.this.parameters
}

output "template" {
  description = "returns a string"
  value       = data.oci_core_cpe_device_shape.this.template
}

output "this" {
  value = oci_core_cpe_device_shape.this
}
```

[top](#index)