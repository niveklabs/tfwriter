# oci_database_autonomous_container_database_dataguard_association_operation

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_container_database_dataguard_association_operation" {
  source = "./modules/oci/r/oci_database_autonomous_container_database_dataguard_association_operation"

  # autonomous_container_database_dataguard_association_id - (required) is a type of string
  autonomous_container_database_dataguard_association_id = null
  # autonomous_container_database_id - (required) is a type of string
  autonomous_container_database_id = null
  # operation - (required) is a type of string
  operation = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autonomous_container_database_dataguard_association_id" {
  description = "(required)"
  type        = string
}

variable "autonomous_container_database_id" {
  description = "(required)"
  type        = string
}

variable "operation" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_autonomous_container_database_dataguard_association_operation" "this" {
  autonomous_container_database_dataguard_association_id = var.autonomous_container_database_dataguard_association_id
  autonomous_container_database_id                       = var.autonomous_container_database_id
  operation                                              = var.operation

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_database_autonomous_container_database_dataguard_association_operation.this.id
}

output "this" {
  value = oci_database_autonomous_container_database_dataguard_association_operation.this
}
```

[top](#index)