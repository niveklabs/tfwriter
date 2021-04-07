# spotinst_ocean_gke_launch_spec_import

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_ocean_gke_launch_spec_import" {
  source = "./modules/spotinst/r/spotinst_ocean_gke_launch_spec_import"

  # node_pool_name - (required) is a type of string
  node_pool_name = null
  # ocean_id - (required) is a type of string
  ocean_id = null
}
```

[top](#index)

### Variables

```terraform
variable "node_pool_name" {
  description = "(required)"
  type        = string
}

variable "ocean_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_ocean_gke_launch_spec_import" "this" {
  # node_pool_name - (required) is a type of string
  node_pool_name = var.node_pool_name
  # ocean_id - (required) is a type of string
  ocean_id = var.ocean_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_ocean_gke_launch_spec_import.this.id
}

output "this" {
  value = spotinst_ocean_gke_launch_spec_import.this
}
```

[top](#index)