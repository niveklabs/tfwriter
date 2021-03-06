# google_data_loss_prevention_deidentify_template

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_data_loss_prevention_deidentify_template" {
  source = "./modules/google/r/google_data_loss_prevention_deidentify_template"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null

  deidentify_config = [{
    info_type_transformations = [{
      transformations = [{
        info_types = [{
          name = null
        }]
        primitive_transformation = [{
          character_mask_config = [{
            characters_to_ignore = [{
              character_to_skip           = null
              common_characters_to_ignore = null
            }]
            masking_character = null
            number_to_mask    = null
            reverse_order     = null
          }]
          replace_config = [{
            new_value = [{
              boolean_value = null
              date_value = [{
                day   = null
                month = null
                year  = null
              }]
              day_of_week_value = null
              float_value       = null
              integer_value     = null
              string_value      = null
              time_value = [{
                hours   = null
                minutes = null
                nanos   = null
                seconds = null
              }]
              timestamp_value = null
            }]
          }]
        }]
      }]
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
variable "description" {
  description = "(optional) - A description of the template."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - User set display name of the template."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - The parent of the template in any of the following formats:\n\n* 'projects/{{project}}'\n* 'projects/{{project}}/locations/{{location}}'\n* 'organizations/{{organization_id}}'\n* 'organizations/{{organization_id}}/locations/{{location}}'"
  type        = string
}

variable "deidentify_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      info_type_transformations = list(object(
        {
          transformations = list(object(
            {
              info_types = list(object(
                {
                  name = string
                }
              ))
              primitive_transformation = list(object(
                {
                  character_mask_config = list(object(
                    {
                      characters_to_ignore = list(object(
                        {
                          character_to_skip           = string
                          common_characters_to_ignore = string
                        }
                      ))
                      masking_character = string
                      number_to_mask    = number
                      reverse_order     = bool
                    }
                  ))
                  replace_config = list(object(
                    {
                      new_value = list(object(
                        {
                          boolean_value = bool
                          date_value = list(object(
                            {
                              day   = number
                              month = number
                              year  = number
                            }
                          ))
                          day_of_week_value = string
                          float_value       = number
                          integer_value     = number
                          string_value      = string
                          time_value = list(object(
                            {
                              hours   = number
                              minutes = number
                              nanos   = number
                              seconds = number
                            }
                          ))
                          timestamp_value = string
                        }
                      ))
                    }
                  ))
                }
              ))
            }
          ))
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
resource "google_data_loss_prevention_deidentify_template" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # parent - (required) is a type of string
  parent = var.parent

  dynamic "deidentify_config" {
    for_each = var.deidentify_config
    content {

      dynamic "info_type_transformations" {
        for_each = deidentify_config.value.info_type_transformations
        content {

          dynamic "transformations" {
            for_each = info_type_transformations.value.transformations
            content {

              dynamic "info_types" {
                for_each = transformations.value.info_types
                content {
                  # name - (required) is a type of string
                  name = info_types.value["name"]
                }
              }

              dynamic "primitive_transformation" {
                for_each = transformations.value.primitive_transformation
                content {

                  dynamic "character_mask_config" {
                    for_each = primitive_transformation.value.character_mask_config
                    content {
                      # masking_character - (optional) is a type of string
                      masking_character = character_mask_config.value["masking_character"]
                      # number_to_mask - (optional) is a type of number
                      number_to_mask = character_mask_config.value["number_to_mask"]
                      # reverse_order - (optional) is a type of bool
                      reverse_order = character_mask_config.value["reverse_order"]

                      dynamic "characters_to_ignore" {
                        for_each = character_mask_config.value.characters_to_ignore
                        content {
                          # character_to_skip - (optional) is a type of string
                          character_to_skip = characters_to_ignore.value["character_to_skip"]
                          # common_characters_to_ignore - (optional) is a type of string
                          common_characters_to_ignore = characters_to_ignore.value["common_characters_to_ignore"]
                        }
                      }

                    }
                  }

                  dynamic "replace_config" {
                    for_each = primitive_transformation.value.replace_config
                    content {

                      dynamic "new_value" {
                        for_each = replace_config.value.new_value
                        content {
                          # boolean_value - (optional) is a type of bool
                          boolean_value = new_value.value["boolean_value"]
                          # day_of_week_value - (optional) is a type of string
                          day_of_week_value = new_value.value["day_of_week_value"]
                          # float_value - (optional) is a type of number
                          float_value = new_value.value["float_value"]
                          # integer_value - (optional) is a type of number
                          integer_value = new_value.value["integer_value"]
                          # string_value - (optional) is a type of string
                          string_value = new_value.value["string_value"]
                          # timestamp_value - (optional) is a type of string
                          timestamp_value = new_value.value["timestamp_value"]

                          dynamic "date_value" {
                            for_each = new_value.value.date_value
                            content {
                              # day - (optional) is a type of number
                              day = date_value.value["day"]
                              # month - (optional) is a type of number
                              month = date_value.value["month"]
                              # year - (optional) is a type of number
                              year = date_value.value["year"]
                            }
                          }

                          dynamic "time_value" {
                            for_each = new_value.value.time_value
                            content {
                              # hours - (optional) is a type of number
                              hours = time_value.value["hours"]
                              # minutes - (optional) is a type of number
                              minutes = time_value.value["minutes"]
                              # nanos - (optional) is a type of number
                              nanos = time_value.value["nanos"]
                              # seconds - (optional) is a type of number
                              seconds = time_value.value["seconds"]
                            }
                          }

                        }
                      }

                    }
                  }

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
output "id" {
  description = "returns a string"
  value       = google_data_loss_prevention_deidentify_template.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_loss_prevention_deidentify_template.this.name
}

output "this" {
  value = google_data_loss_prevention_deidentify_template.this
}
```

[top](#index)