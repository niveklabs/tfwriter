# google_data_loss_prevention_inspect_template

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
module "google_data_loss_prevention_inspect_template" {
  source = "./modules/google/r/google_data_loss_prevention_inspect_template"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null

  inspect_config = [{
    content_options = []
    custom_info_types = [{
      dictionary = [{
        cloud_storage_path = [{
          path = null
        }]
        word_list = [{
          words = []
        }]
      }]
      exclusion_type = null
      info_type = [{
        name = null
      }]
      likelihood = null
      regex = [{
        group_indexes = []
        pattern       = null
      }]
      stored_type = [{
        name = null
      }]
    }]
    exclude_info_types = null
    include_quote      = null
    info_types = [{
      name = null
    }]
    limits = [{
      max_findings_per_info_type = [{
        info_type = [{
          name = null
        }]
        max_findings = null
      }]
      max_findings_per_item    = null
      max_findings_per_request = null
    }]
    min_likelihood = null
    rule_set = [{
      info_types = [{
        name = null
      }]
      rules = [{
        exclusion_rule = [{
          dictionary = [{
            cloud_storage_path = [{
              path = null
            }]
            word_list = [{
              words = []
            }]
          }]
          exclude_info_types = [{
            info_types = [{
              name = null
            }]
          }]
          matching_type = null
          regex = [{
            group_indexes = []
            pattern       = null
          }]
        }]
        hotword_rule = [{
          hotword_regex = [{
            group_indexes = []
            pattern       = null
          }]
          likelihood_adjustment = [{
            fixed_likelihood    = null
            relative_likelihood = null
          }]
          proximity = [{
            window_after  = null
            window_before = null
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
  description = "(optional) - A description of the inspect template."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - User set display name of the inspect template."
  type        = string
  default     = null
}

variable "parent" {
  description = "(required) - The parent of the inspect template in any of the following formats:\n\n* 'projects/{{project}}'\n* 'projects/{{project}}/locations/{{location}}'\n* 'organizations/{{organization_id}}'\n* 'organizations/{{organization_id}}/locations/{{location}}'"
  type        = string
}

variable "inspect_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_options = list(string)
      custom_info_types = list(object(
        {
          dictionary = list(object(
            {
              cloud_storage_path = list(object(
                {
                  path = string
                }
              ))
              word_list = list(object(
                {
                  words = list(string)
                }
              ))
            }
          ))
          exclusion_type = string
          info_type = list(object(
            {
              name = string
            }
          ))
          likelihood = string
          regex = list(object(
            {
              group_indexes = list(number)
              pattern       = string
            }
          ))
          stored_type = list(object(
            {
              name = string
            }
          ))
        }
      ))
      exclude_info_types = bool
      include_quote      = bool
      info_types = list(object(
        {
          name = string
        }
      ))
      limits = list(object(
        {
          max_findings_per_info_type = list(object(
            {
              info_type = list(object(
                {
                  name = string
                }
              ))
              max_findings = number
            }
          ))
          max_findings_per_item    = number
          max_findings_per_request = number
        }
      ))
      min_likelihood = string
      rule_set = list(object(
        {
          info_types = list(object(
            {
              name = string
            }
          ))
          rules = list(object(
            {
              exclusion_rule = list(object(
                {
                  dictionary = list(object(
                    {
                      cloud_storage_path = list(object(
                        {
                          path = string
                        }
                      ))
                      word_list = list(object(
                        {
                          words = list(string)
                        }
                      ))
                    }
                  ))
                  exclude_info_types = list(object(
                    {
                      info_types = list(object(
                        {
                          name = string
                        }
                      ))
                    }
                  ))
                  matching_type = string
                  regex = list(object(
                    {
                      group_indexes = list(number)
                      pattern       = string
                    }
                  ))
                }
              ))
              hotword_rule = list(object(
                {
                  hotword_regex = list(object(
                    {
                      group_indexes = list(number)
                      pattern       = string
                    }
                  ))
                  likelihood_adjustment = list(object(
                    {
                      fixed_likelihood    = string
                      relative_likelihood = number
                    }
                  ))
                  proximity = list(object(
                    {
                      window_after  = number
                      window_before = number
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
resource "google_data_loss_prevention_inspect_template" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # parent - (required) is a type of string
  parent = var.parent

  dynamic "inspect_config" {
    for_each = var.inspect_config
    content {
      # content_options - (optional) is a type of list of string
      content_options = inspect_config.value["content_options"]
      # exclude_info_types - (optional) is a type of bool
      exclude_info_types = inspect_config.value["exclude_info_types"]
      # include_quote - (optional) is a type of bool
      include_quote = inspect_config.value["include_quote"]
      # min_likelihood - (optional) is a type of string
      min_likelihood = inspect_config.value["min_likelihood"]

      dynamic "custom_info_types" {
        for_each = inspect_config.value.custom_info_types
        content {
          # exclusion_type - (optional) is a type of string
          exclusion_type = custom_info_types.value["exclusion_type"]
          # likelihood - (optional) is a type of string
          likelihood = custom_info_types.value["likelihood"]

          dynamic "dictionary" {
            for_each = custom_info_types.value.dictionary
            content {

              dynamic "cloud_storage_path" {
                for_each = dictionary.value.cloud_storage_path
                content {
                  # path - (required) is a type of string
                  path = cloud_storage_path.value["path"]
                }
              }

              dynamic "word_list" {
                for_each = dictionary.value.word_list
                content {
                  # words - (required) is a type of list of string
                  words = word_list.value["words"]
                }
              }

            }
          }

          dynamic "info_type" {
            for_each = custom_info_types.value.info_type
            content {
              # name - (required) is a type of string
              name = info_type.value["name"]
            }
          }

          dynamic "regex" {
            for_each = custom_info_types.value.regex
            content {
              # group_indexes - (optional) is a type of list of number
              group_indexes = regex.value["group_indexes"]
              # pattern - (required) is a type of string
              pattern = regex.value["pattern"]
            }
          }

          dynamic "stored_type" {
            for_each = custom_info_types.value.stored_type
            content {
              # name - (required) is a type of string
              name = stored_type.value["name"]
            }
          }

        }
      }

      dynamic "info_types" {
        for_each = inspect_config.value.info_types
        content {
          # name - (required) is a type of string
          name = info_types.value["name"]
        }
      }

      dynamic "limits" {
        for_each = inspect_config.value.limits
        content {
          # max_findings_per_item - (required) is a type of number
          max_findings_per_item = limits.value["max_findings_per_item"]
          # max_findings_per_request - (required) is a type of number
          max_findings_per_request = limits.value["max_findings_per_request"]

          dynamic "max_findings_per_info_type" {
            for_each = limits.value.max_findings_per_info_type
            content {
              # max_findings - (required) is a type of number
              max_findings = max_findings_per_info_type.value["max_findings"]

              dynamic "info_type" {
                for_each = max_findings_per_info_type.value.info_type
                content {
                  # name - (required) is a type of string
                  name = info_type.value["name"]
                }
              }

            }
          }

        }
      }

      dynamic "rule_set" {
        for_each = inspect_config.value.rule_set
        content {

          dynamic "info_types" {
            for_each = rule_set.value.info_types
            content {
              # name - (required) is a type of string
              name = info_types.value["name"]
            }
          }

          dynamic "rules" {
            for_each = rule_set.value.rules
            content {

              dynamic "exclusion_rule" {
                for_each = rules.value.exclusion_rule
                content {
                  # matching_type - (required) is a type of string
                  matching_type = exclusion_rule.value["matching_type"]

                  dynamic "dictionary" {
                    for_each = exclusion_rule.value.dictionary
                    content {

                      dynamic "cloud_storage_path" {
                        for_each = dictionary.value.cloud_storage_path
                        content {
                          # path - (required) is a type of string
                          path = cloud_storage_path.value["path"]
                        }
                      }

                      dynamic "word_list" {
                        for_each = dictionary.value.word_list
                        content {
                          # words - (required) is a type of list of string
                          words = word_list.value["words"]
                        }
                      }

                    }
                  }

                  dynamic "exclude_info_types" {
                    for_each = exclusion_rule.value.exclude_info_types
                    content {

                      dynamic "info_types" {
                        for_each = exclude_info_types.value.info_types
                        content {
                          # name - (required) is a type of string
                          name = info_types.value["name"]
                        }
                      }

                    }
                  }

                  dynamic "regex" {
                    for_each = exclusion_rule.value.regex
                    content {
                      # group_indexes - (optional) is a type of list of number
                      group_indexes = regex.value["group_indexes"]
                      # pattern - (required) is a type of string
                      pattern = regex.value["pattern"]
                    }
                  }

                }
              }

              dynamic "hotword_rule" {
                for_each = rules.value.hotword_rule
                content {

                  dynamic "hotword_regex" {
                    for_each = hotword_rule.value.hotword_regex
                    content {
                      # group_indexes - (optional) is a type of list of number
                      group_indexes = hotword_regex.value["group_indexes"]
                      # pattern - (required) is a type of string
                      pattern = hotword_regex.value["pattern"]
                    }
                  }

                  dynamic "likelihood_adjustment" {
                    for_each = hotword_rule.value.likelihood_adjustment
                    content {
                      # fixed_likelihood - (optional) is a type of string
                      fixed_likelihood = likelihood_adjustment.value["fixed_likelihood"]
                      # relative_likelihood - (optional) is a type of number
                      relative_likelihood = likelihood_adjustment.value["relative_likelihood"]
                    }
                  }

                  dynamic "proximity" {
                    for_each = hotword_rule.value.proximity
                    content {
                      # window_after - (optional) is a type of number
                      window_after = proximity.value["window_after"]
                      # window_before - (optional) is a type of number
                      window_before = proximity.value["window_before"]
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
  value       = google_data_loss_prevention_inspect_template.this.id
}

output "name" {
  description = "returns a string"
  value       = google_data_loss_prevention_inspect_template.this.name
}

output "this" {
  value = google_data_loss_prevention_inspect_template.this
}
```

[top](#index)