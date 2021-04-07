# oci_core_volume_backup_policy_assignment

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_core_volume_backup_policy_assignment" {
  source = "./modules/oci/r/oci_core_volume_backup_policy_assignment"

  # asset_id - (required) is a type of string
  asset_id = null
  # policy_id - (required) is a type of string
  policy_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "policy_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_volume_backup_policy_assignment" "this" {
  asset_id  = var.asset_id
  policy_id = var.policy_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy_assignment.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume_backup_policy_assignment.this.time_created
}

output "this" {
  value = oci_core_volume_backup_policy_assignment.this
}
```

[top](#index)