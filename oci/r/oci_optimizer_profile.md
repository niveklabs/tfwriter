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
    oci = ">= 4.21.0"
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

  target_compartments = [{
    items = []
  }]

  target_tags = [{
    items = [{
      tag_definition_name = null
      tag_namespace_name  = null
      tag_value_type      = null
      tag_values          = []
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

variable "target_compartments" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      items = list(string)
    }
  ))
  default = []
}

variable "target_tags" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      items = list(object(
        {
          tag_definition_name = string
          tag_namespace_name  = string
          tag_value_type      = string
          tag_values          = list(string)
        }
      ))
    }
  ))
  default = []
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
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (required) is a type of string
  description = var.description
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # name - (required) is a type of string
  name = var.name

  dynamic "levels_configuration" {
    for_each = var.levels_configuration
    content {

      dynamic "items" {
        for_each = levels_configuration.value.items
        content {
          # level - (optional) is a type of string
          level = items.value["level"]
          # recommendation_id - (optional) is a type of string
          recommendation_id = items.value["recommendation_id"]
        }
      }

    }
  }

  dynamic "target_compartments" {
    for_each = var.target_compartments
    content {
      # items - (required) is a type of list of string
      items = target_compartments.value["items"]
    }
  }

  dynamic "target_tags" {
    for_each = var.target_tags
    content {

      dynamic "items" {
        for_each = target_tags.value.items
        content {
          # tag_definition_name - (required) is a type of string
          tag_definition_name = items.value["tag_definition_name"]
          # tag_namespace_name - (required) is a type of string
          tag_namespace_name = items.value["tag_namespace_name"]
          # tag_value_type - (required) is a type of string
          tag_value_type = items.value["tag_value_type"]
          # tag_values - (optional) is a type of list of string
          tag_values = items.value["tag_values"]
        }
      }

    }
  }

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