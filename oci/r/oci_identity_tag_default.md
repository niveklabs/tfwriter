# oci_identity_tag_default

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
module "oci_identity_tag_default" {
  source = "./modules/oci/r/oci_identity_tag_default"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # is_required - (optional) is a type of bool
  is_required = null
  # tag_definition_id - (required) is a type of string
  tag_definition_id = null
  # value - (required) is a type of string
  value = null

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
  description = "(required)"
  type        = string
}

variable "is_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tag_definition_id" {
  description = "(required)"
  type        = string
}

variable "value" {
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
resource "oci_identity_tag_default" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # is_required - (optional) is a type of bool
  is_required = var.is_required
  # tag_definition_id - (required) is a type of string
  tag_definition_id = var.tag_definition_id
  # value - (required) is a type of string
  value = var.value

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
  value       = oci_identity_tag_default.this.id
}

output "is_required" {
  description = "returns a bool"
  value       = oci_identity_tag_default.this.is_required
}

output "state" {
  description = "returns a string"
  value       = oci_identity_tag_default.this.state
}

output "tag_definition_name" {
  description = "returns a string"
  value       = oci_identity_tag_default.this.tag_definition_name
}

output "tag_namespace_id" {
  description = "returns a string"
  value       = oci_identity_tag_default.this.tag_namespace_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_tag_default.this.time_created
}

output "this" {
  value = oci_identity_tag_default.this
}
```

[top](#index)