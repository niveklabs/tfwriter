# oci_kms_vault_replication

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
module "oci_kms_vault_replication" {
  source = "./modules/oci/r/oci_kms_vault_replication"

  # replica_region - (required) is a type of string
  replica_region = null
  # vault_id - (required) is a type of string
  vault_id = null

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
variable "replica_region" {
  description = "(required)"
  type        = string
}

variable "vault_id" {
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
resource "oci_kms_vault_replication" "this" {
  replica_region = var.replica_region
  vault_id       = var.vault_id

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
  value       = oci_kms_vault_replication.this.id
}

output "this" {
  value = oci_kms_vault_replication.this
}
```

[top](#index)