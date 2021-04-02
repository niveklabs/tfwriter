# oci_core_cross_connect_status

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
module "oci_core_cross_connect_status" {
  source = "./modules/oci/d/oci_core_cross_connect_status"

  # cross_connect_id - (required) is a type of string
  cross_connect_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cross_connect_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_cross_connect_status" "this" {
  cross_connect_id = var.cross_connect_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_status.this.id
}

output "interface_state" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_status.this.interface_state
}

output "light_level_ind_bm" {
  description = "returns a number"
  value       = data.oci_core_cross_connect_status.this.light_level_ind_bm
}

output "light_level_indicator" {
  description = "returns a string"
  value       = data.oci_core_cross_connect_status.this.light_level_indicator
}

output "this" {
  value = oci_core_cross_connect_status.this
}
```

[top](#index)