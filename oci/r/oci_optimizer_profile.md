# oci_optimizer_profile

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
module "oci_optimizer_profile" {
  source = "./modules/oci/r/oci_optimizer_profile"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null

  levels_configuration = [{
    items = [{
      level             = null
      recommendation_id = null
    }]
  }]

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

variable "name" {
  description = "(required)"
  type        = string
}

variable "levels_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      items = list(object(
        {
          level             = string
          recommendation_id = string
        }
      ))
    }
  ))
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
resource "oci_optimizer_profile" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  freeform_tags  = var.freeform_tags
  name           = var.name

  dynamic "levels_configuration" {
    for_each = var.levels_configuration
    content {

      dynamic "items" {
        for_each = levels_configuration.value.items
        content {
          level             = items.value["level"]
          recommendation_id = items.value["recommendation_id"]
        }
      }

    }
  }

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_optimizer_profile.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_optimizer_profile.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_optimizer_profile.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_optimizer_profile.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_optimizer_profile.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_optimizer_profile.this.time_updated
}

output "this" {
  value = oci_optimizer_profile.this
}
```

[top](#index)