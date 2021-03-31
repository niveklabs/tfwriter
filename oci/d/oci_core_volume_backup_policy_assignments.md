# oci_core_volume_backup_policy_assignments

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
module "oci_core_volume_backup_policy_assignments" {
  source = "./modules/oci/d/oci_core_volume_backup_policy_assignments"

  # asset_id - (required) is a type of string
  asset_id = null

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
variable "asset_id" {
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
data "oci_core_volume_backup_policy_assignments" "this" {
  asset_id = var.asset_id

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
  value       = data.oci_core_volume_backup_policy_assignments.this.id
}

output "volume_backup_policy_assignments" {
  description = "returns a list of object"
  value       = data.oci_core_volume_backup_policy_assignments.this.volume_backup_policy_assignments
}

output "this" {
  value = oci_core_volume_backup_policy_assignments.this
}
```

[top](#index)