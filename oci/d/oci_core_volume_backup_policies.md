# oci_core_volume_backup_policies

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
module "oci_core_volume_backup_policies" {
  source = "./modules/oci/d/oci_core_volume_backup_policies"

  # compartment_id - (optional) is a type of string
  compartment_id = null

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
data "oci_core_volume_backup_policies" "this" {
  compartment_id = var.compartment_id

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
  value       = data.oci_core_volume_backup_policies.this.id
}

output "volume_backup_policies" {
  description = "returns a list of object"
  value       = data.oci_core_volume_backup_policies.this.volume_backup_policies
}

output "this" {
  value = oci_core_volume_backup_policies.this
}
```

[top](#index)