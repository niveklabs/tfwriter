# oci_identity_idp_group_mapping

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
module "oci_identity_idp_group_mapping" {
  source = "./modules/oci/r/oci_identity_idp_group_mapping"

  # group_id - (required) is a type of string
  group_id = null
  # identity_provider_id - (required) is a type of string
  identity_provider_id = null
  # idp_group_name - (required) is a type of string
  idp_group_name = null

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
variable "group_id" {
  description = "(required)"
  type        = string
}

variable "identity_provider_id" {
  description = "(required)"
  type        = string
}

variable "idp_group_name" {
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
resource "oci_identity_idp_group_mapping" "this" {
  group_id             = var.group_id
  identity_provider_id = var.identity_provider_id
  idp_group_name       = var.idp_group_name

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
  value       = oci_identity_idp_group_mapping.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_identity_idp_group_mapping.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_idp_group_mapping.this.inactive_state
}

output "state" {
  description = "returns a string"
  value       = oci_identity_idp_group_mapping.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_idp_group_mapping.this.time_created
}

output "this" {
  value = oci_identity_idp_group_mapping.this
}
```

[top](#index)