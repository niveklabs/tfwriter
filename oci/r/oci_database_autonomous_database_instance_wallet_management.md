# oci_database_autonomous_database_instance_wallet_management

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
module "oci_database_autonomous_database_instance_wallet_management" {
  source = "./modules/oci/r/oci_database_autonomous_database_instance_wallet_management"

  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = null
  # should_rotate - (optional) is a type of bool
  should_rotate = null

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
variable "autonomous_database_id" {
  description = "(required)"
  type        = string
}

variable "should_rotate" {
  description = "(optional)"
  type        = bool
  default     = null
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
resource "oci_database_autonomous_database_instance_wallet_management" "this" {
  # autonomous_database_id - (required) is a type of string
  autonomous_database_id = var.autonomous_database_id
  # should_rotate - (optional) is a type of bool
  should_rotate = var.should_rotate

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = oci_database_autonomous_database_instance_wallet_management.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_database_instance_wallet_management.this.state
}

output "time_rotated" {
  description = "returns a string"
  value       = oci_database_autonomous_database_instance_wallet_management.this.time_rotated
}

output "this" {
  value = oci_database_autonomous_database_instance_wallet_management.this
}
```

[top](#index)