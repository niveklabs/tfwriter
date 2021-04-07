# oci_identity_tag

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
module "oci_identity_tag" {
  source = "./modules/oci/r/oci_identity_tag"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_cost_tracking - (optional) is a type of bool
  is_cost_tracking = null
  # is_retired - (optional) is a type of bool
  is_retired = null
  # name - (required) is a type of string
  name = null
  # tag_namespace_id - (required) is a type of string
  tag_namespace_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  validator = [{
    validator_type = null
    values         = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_cost_tracking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_retired" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tag_namespace_id" {
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

variable "validator" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      validator_type = string
      values         = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_identity_tag" "this" {
  defined_tags     = var.defined_tags
  description      = var.description
  freeform_tags    = var.freeform_tags
  is_cost_tracking = var.is_cost_tracking
  is_retired       = var.is_retired
  name             = var.name
  tag_namespace_id = var.tag_namespace_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "validator" {
    for_each = var.validator
    content {
      validator_type = validator.value["validator_type"]
      values         = validator.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_tag.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_tag.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_tag.this.id
}

output "is_cost_tracking" {
  description = "returns a bool"
  value       = oci_identity_tag.this.is_cost_tracking
}

output "is_retired" {
  description = "returns a bool"
  value       = oci_identity_tag.this.is_retired
}

output "state" {
  description = "returns a string"
  value       = oci_identity_tag.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_tag.this.time_created
}

output "this" {
  value = oci_identity_tag.this
}
```

[top](#index)