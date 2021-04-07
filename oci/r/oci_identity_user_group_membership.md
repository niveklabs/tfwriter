# oci_identity_user_group_membership

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
module "oci_identity_user_group_membership" {
  source = "./modules/oci/r/oci_identity_user_group_membership"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # group_id - (required) is a type of string
  group_id = null
  # user_id - (required) is a type of string
  user_id = null

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
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
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
resource "oci_identity_user_group_membership" "this" {
  compartment_id = var.compartment_id
  group_id       = var.group_id
  user_id        = var.user_id

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_identity_user_group_membership.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_identity_user_group_membership.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_user_group_membership.this.inactive_state
}

output "state" {
  description = "returns a string"
  value       = oci_identity_user_group_membership.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_user_group_membership.this.time_created
}

output "this" {
  value = oci_identity_user_group_membership.this
}
```

[top](#index)