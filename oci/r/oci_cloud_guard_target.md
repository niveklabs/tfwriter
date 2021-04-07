# oci_cloud_guard_target

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
module "oci_cloud_guard_target" {
  source = "./modules/oci/r/oci_cloud_guard_target"

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
  # state - (optional) is a type of string
  state = null
  # target_resource_id - (required) is a type of string
  target_resource_id = null
  # target_resource_type - (required) is a type of string
  target_resource_type = null

  target_detector_recipes = [{
    compartment_id     = null
    description        = null
    detector           = null
    detector_recipe_id = null
    detector_rules = [{
      description = null
      details = [{
        condition_groups = [{
          compartment_id = null
          condition      = null
        }]
        configurations = [{
          config_key = null
          data_type  = null
          name       = null
          value      = null
          values = [{
            list_type         = null
            managed_list_type = null
            value             = null
          }]
        }]
        is_configuration_allowed = null
        is_enabled               = null
        labels                   = []
        risk_level               = null
      }]
      detector           = null
      detector_rule_id   = null
      display_name       = null
      lifecycle_details  = null
      managed_list_types = []
      recommendation     = null
      resource_type      = null
      service_type       = null
      state              = null
      time_created       = null
      time_updated       = null
    }]
    display_name = null
    effective_detector_rules = [{
      description = null
      details = [{
        condition_groups = [{
          compartment_id = null
          condition      = null
        }]
        configurations = [{
          config_key = null
          data_type  = null
          name       = null
          value      = null
          values = [{
            list_type         = null
            managed_list_type = null
            value             = null
          }]
        }]
        is_configuration_allowed = null
        is_enabled               = null
        labels                   = []
        risk_level               = null
      }]
      detector           = null
      detector_rule_id   = null
      display_name       = null
      lifecycle_details  = null
      managed_list_types = []
      recommendation     = null
      resource_type      = null
      service_type       = null
      state              = null
      time_created       = null
      time_updated       = null
    }]
    id           = null
    owner        = null
    state        = null
    time_created = null
    time_updated = null
  }]

  target_responder_recipes = [{
    compartment_id = null
    description    = null
    display_name   = null
    effective_responder_rules = [{
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
    id                  = null
    owner               = null
    responder_recipe_id = null
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
    time_created = null
    time_updated = null
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_resource_id" {
  description = "(required)"
  type        = string
}

variable "target_resource_type" {
  description = "(required)"
  type        = string
}

variable "target_detector_recipes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      compartment_id     = string
      description        = string
      detector           = string
      detector_recipe_id = string
      detector_rules = list(object(
        {
          description = string
          details = list(object(
            {
              condition_groups = list(object(
                {
                  compartment_id = string
                  condition      = string
                }
              ))
              configurations = list(object(
                {
                  config_key = string
                  data_type  = string
                  name       = string
                  value      = string
                  values = list(object(
                    {
                      list_type         = string
                      managed_list_type = string
                      value             = string
                    }
                  ))
                }
              ))
              is_configuration_allowed = bool
              is_enabled               = bool
              labels                   = list(string)
              risk_level               = string
            }
          ))
          detector           = string
          detector_rule_id   = string
          display_name       = string
          lifecycle_details  = string
          managed_list_types = list(string)
          recommendation     = string
          resource_type      = string
          service_type       = string
          state              = string
          time_created       = string
          time_updated       = string
        }
      ))
      display_name = string
      effective_detector_rules = list(object(
        {
          description = string
          details = list(object(
            {
              condition_groups = list(object(
                {
                  compartment_id = string
                  condition      = string
                }
              ))
              configurations = list(object(
                {
                  config_key = string
                  data_type  = string
                  name       = string
                  value      = string
                  values = list(object(
                    {
                      list_type         = string
                      managed_list_type = string
                      value             = string
                    }
                  ))
                }
              ))
              is_configuration_allowed = bool
              is_enabled               = bool
              labels                   = list(string)
              risk_level               = string
            }
          ))
          detector           = string
          detector_rule_id   = string
          display_name       = string
          lifecycle_details  = string
          managed_list_types = list(string)
          recommendation     = string
          resource_type      = string
          service_type       = string
          state              = string
          time_created       = string
          time_updated       = string
        }
      ))
      id           = string
      owner        = string
      state        = string
      time_created = string
      time_updated = string
    }
  ))
  default = []
}

variable "target_responder_recipes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      compartment_id = string
      description    = string
      display_name   = string
      effective_responder_rules = list(object(
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
      id                  = string
      owner               = string
      responder_recipe_id = string
      responder_rules = list(object(
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
      time_created = string
      time_updated = string
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
resource "oci_cloud_guard_target" "this" {
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
  # state - (optional) is a type of string
  state = var.state
  # target_resource_id - (required) is a type of string
  target_resource_id = var.target_resource_id
  # target_resource_type - (required) is a type of string
  target_resource_type = var.target_resource_type

  dynamic "target_detector_recipes" {
    for_each = var.target_detector_recipes
    content {
      # detector_recipe_id - (required) is a type of string
      detector_recipe_id = target_detector_recipes.value["detector_recipe_id"]

      dynamic "detector_rules" {
        for_each = target_detector_recipes.value.detector_rules
        content {
          # detector_rule_id - (required) is a type of string
          detector_rule_id = detector_rules.value["detector_rule_id"]

          dynamic "details" {
            for_each = detector_rules.value.details
            content {

              dynamic "condition_groups" {
                for_each = details.value.condition_groups
                content {
                  # compartment_id - (required) is a type of string
                  compartment_id = condition_groups.value["compartment_id"]
                  # condition - (required) is a type of string
                  condition = condition_groups.value["condition"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "target_responder_recipes" {
    for_each = var.target_responder_recipes
    content {
      # responder_recipe_id - (required) is a type of string
      responder_recipe_id = target_responder_recipes.value["responder_recipe_id"]

      dynamic "responder_rules" {
        for_each = target_responder_recipes.value.responder_rules
        content {
          # responder_rule_id - (required) is a type of string
          responder_rule_id = responder_rules.value["responder_rule_id"]

          dynamic "details" {
            for_each = responder_rules.value.details
            content {
              # condition - (optional) is a type of string
              condition = details.value["condition"]
              # mode - (optional) is a type of string
              mode = details.value["mode"]

              dynamic "configurations" {
                for_each = details.value.configurations
                content {
                  # config_key - (required) is a type of string
                  config_key = configurations.value["config_key"]
                  # name - (required) is a type of string
                  name = configurations.value["name"]
                  # value - (required) is a type of string
                  value = configurations.value["value"]
                }
              }

            }
          }

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
  value       = oci_cloud_guard_target.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_target.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.id
}

output "inherited_by_compartments" {
  description = "returns a list of string"
  value       = oci_cloud_guard_target.this.inherited_by_compartments
}

output "lifecyle_details" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.lifecyle_details
}

output "recipe_count" {
  description = "returns a number"
  value       = oci_cloud_guard_target.this.recipe_count
}

output "state" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_target.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_cloud_guard_target.this.time_updated
}

output "this" {
  value = oci_cloud_guard_target.this
}
```

[top](#index)