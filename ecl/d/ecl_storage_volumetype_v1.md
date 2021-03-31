# ecl_storage_volumetype_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_storage_volumetype_v1" {
  source = "./modules/ecl/d/ecl_storage_volumetype_v1"

  # name - (optional) is a type of string
  name = null
  # volume_type_id - (optional) is a type of string
  volume_type_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_type_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_storage_volumetype_v1" "this" {
  name           = var.name
  volume_type_id = var.volume_type_id
}
```

[top](#index)

### Outputs

```terraform
output "extra_specs" {
  description = "returns a map of string"
  value       = data.ecl_storage_volumetype_v1.this.extra_specs
}

output "id" {
  description = "returns a string"
  value       = data.ecl_storage_volumetype_v1.this.id
}

output "this" {
  value = ecl_storage_volumetype_v1.this
}
```

[top](#index)