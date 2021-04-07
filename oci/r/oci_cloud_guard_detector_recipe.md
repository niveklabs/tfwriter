# oci_cloud_guard_detector_recipe

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
module "oci_cloud_guard_detector_recipe" {
  source = "./modules/oci/r/oci_cloud_guard_detector_recipe"

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
  # source_detector_recipe_id - (required) is a type of string
  source_detector_recipe_id = null

  detector_rules = [{
    candidate_responder_rules = [{
      display_name = null
      id           = null
      is_preferred = null
    }]
    description = null
    details = [{
      condition = null
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

variable "source_detector_recipe_id" {
  description = "(required)"
  type        = string
}

variable "detector_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      candidate_responder_rules = list(object(
        {
          display_name = string
          id           = string
          is_preferred = bool
        }
      ))
      description = string
      details = list(object(
        {
          condition = string
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
resource "oci_cloud_guard_detector_recipe" "this" {
  compartment_id            = var.compartment_id
  defined_tags              = var.defined_tags
  description               = var.description
  display_name              = var.display_name
  freeform_tags             = var.freeform_tags
  source_detector_recipe_id = var.source_detector_recipe_id

  dynamic "detector_rules" {
    for_each = var.detector_rules
    content {
      detector_rule_id = detector_rules.value["detector_rule_id"]

      dynamic "details" {
        for_each = detector_rules.value.details
        content {
          condition  = details.value["condition"]
          is_enabled = details.value["is_enabled"]
          labels     = details.value["labels"]
          risk_level = details.value["risk_level"]

          dynamic "configurations" {
            for_each = details.value.configurations
            content {
              config_key = configurations.value["config_key"]
              data_type  = configurations.value["data_type"]
              name       = configurations.value["name"]
              value      = configurations.value["value"]

              dynamic "values" {
                for_each = configurations.value.values
                content {
                  list_type         = values.value["list_type"]
                  managed_list_type = values.value["managed_list_type"]
                  value             = values.value["value"]
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
  value       = oci_cloud_guard_detector_recipe.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.description
}

output "detector" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.detector
}

output "effective_detector_rules" {
  description = "returns a list of object"
  value       = oci_cloud_guard_detector_recipe.this.effective_detector_rules
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_detector_recipe.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.id
}

output "owner" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.owner
}

output "state" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_cloud_guard_detector_recipe.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_cloud_guard_detector_recipe.this.time_updated
}

output "this" {
  value = oci_cloud_guard_detector_recipe.this
}
```

[top](#index)