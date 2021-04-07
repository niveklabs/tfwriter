# oci_cloud_guard_responder_recipe

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
module "oci_cloud_guard_responder_recipe" {
  source = "./modules/oci/r/oci_cloud_guard_responder_recipe"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # source_responder_recipe_id - (required) is a type of string
  source_responder_recipe_id = null

  responder_rules = [{
    compartment_id = null
    description    = null
    details = [{
      condition = null
      configurations = [{
        config_key = null
        name       = null
        value      = null
      }]
      is_enabled = null
      mode       = null
    }]
    display_name      = null
    lifecycle_details = null
    policies          = []
    responder_rule_id = null
    state             = null
    supported_modes   = []
    time_created      = null
    time_updated      = null
    type              = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_responder_recipe_id" {
  description = "(required)"
  type        = string
}

variable "responder_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      compartment_id = string
      description    = string
      details = list(object(
        {
          condition = string
          configurations = list(object(
            {
              config_key = string
              name       = string
              value      = string
            }
          ))
          is_enabled = bool
          mode       = string
        }
      ))
      display_name      = string
      lifecycle_details = string
      policies          = list(string)
      responder_rule_id = string
      state             = string
      supported_modes   = list(string)
      time_created      = string
      time_updated      = string
      type              = string
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
resource "oci_cloud_guard_responder_recipe" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # source_responder_recipe_id - (required) is a type of string
  source_responder_recipe_id = var.source_responder_recipe_id

  dynamic "responder_rules" {
    for_each = var.responder_rules
    content {
      # compartment_id - (optional) is a type of string
      compartment_id = responder_rules.value["compartment_id"]
      # responder_rule_id - (required) is a type of string
      responder_rule_id = responder_rules.value["responder_rule_id"]

      dynamic "details" {
        for_each = responder_rules.value.details
        content {
          # is_enabled - (required) is a type of bool
          is_enabled = details.value["is_enabled"]
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
  value       = oci_cloud_guard_responder_recipe.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.description
}

output "effective_responder_rules" {
  description = "returns a list of object"
  value       = oci_cloud_guard_responder_recipe.this.effective_responder_rules
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_responder_recipe.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.lifecycle_details
}

output "owner" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.owner
}

output "state" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_responder_recipe.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_cloud_guard_responder_recipe.this.time_updated
}

output "this" {
  value = oci_cloud_guard_responder_recipe.this
}
```

[top](#index)