# oci_database_autonomous_database_regional_wallet_management

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_autonomous_database_regional_wallet_management" {
  source = "./modules/oci/r/oci_database_autonomous_database_regional_wallet_management"

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
resource "oci_database_autonomous_database_regional_wallet_management" "this" {
  should_rotate = var.should_rotate

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
  value       = oci_database_autonomous_database_regional_wallet_management.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_database_autonomous_database_regional_wallet_management.this.state
}

output "time_rotated" {
  description = "returns a string"
  value       = oci_database_autonomous_database_regional_wallet_management.this.time_rotated
}

output "this" {
  value = oci_database_autonomous_database_regional_wallet_management.this
}
```

[top](#index)