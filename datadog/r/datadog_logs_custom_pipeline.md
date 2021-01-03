# datadog_logs_custom_pipeline

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_logs_custom_pipeline" {
  source = "./modules/datadog/r/datadog_logs_custom_pipeline"

  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # name - (required) is a type of string
  name = null

  filter = [{
    query = null
  }]

  processor = [{
    arithmetic_processor = [{
      expression         = null
      is_enabled         = null
      is_replace_missing = null
      name               = null
      target             = null
    }]
    attribute_remapper = [{
      is_enabled           = null
      name                 = null
      override_on_conflict = null
      preserve_source      = null
      source_type          = null
      sources              = []
      target               = null
      target_format        = null
      target_type          = null
    }]
    category_processor = [{
      category = [{
        filter = [{
          query = null
        }]
        name = null
      }]
      is_enabled = null
      name       = null
      target     = null
    }]
    date_remapper = [{
      is_enabled = null
      name       = null
      sources    = []
    }]
    geo_ip_parser = [{
      is_enabled = null
      name       = null
      sources    = []
      target     = null
    }]
    grok_parser = [{
      grok = [{
        match_rules   = null
        support_rules = null
      }]
      is_enabled = null
      name       = null
      samples    = []
      source     = null
    }]
    lookup_processor = [{
      default_lookup = null
      is_enabled     = null
      lookup_table   = []
      name           = null
      source         = null
      target         = null
    }]
    message_remapper = [{
      is_enabled = null
      name       = null
      sources    = []
    }]
    pipeline = [{
      filter = [{
        query = null
      }]
      is_enabled = null
      name       = null
      processor = [{
        arithmetic_processor = [{
          expression         = null
          is_enabled         = null
          is_replace_missing = null
          name               = null
          target             = null
        }]
        attribute_remapper = [{
          is_enabled           = null
          name                 = null
          override_on_conflict = null
          preserve_source      = null
          source_type          = null
          sources              = []
          target               = null
          target_format        = null
          target_type          = null
        }]
        category_processor = [{
          category = [{
            filter = [{
              query = null
            }]
            name = null
          }]
          is_enabled = null
          name       = null
          target     = null
        }]
        date_remapper = [{
          is_enabled = null
          name       = null
          sources    = []
        }]
        geo_ip_parser = [{
          is_enabled = null
          name       = null
          sources    = []
          target     = null
        }]
        grok_parser = [{
          grok = [{
            match_rules   = null
            support_rules = null
          }]
          is_enabled = null
          name       = null
          samples    = []
          source     = null
        }]
        lookup_processor = [{
          default_lookup = null
          is_enabled     = null
          lookup_table   = []
          name           = null
          source         = null
          target         = null
        }]
        message_remapper = [{
          is_enabled = null
          name       = null
          sources    = []
        }]
        service_remapper = [{
          is_enabled = null
          name       = null
          sources    = []
        }]
        status_remapper = [{
          is_enabled = null
          name       = null
          sources    = []
        }]
        string_builder_processor = [{
          is_enabled         = null
          is_replace_missing = null
          name               = null
          target             = null
          template           = null
        }]
        trace_id_remapper = [{
          is_enabled = null
          name       = null
          sources    = []
        }]
        url_parser = [{
          is_enabled               = null
          name                     = null
          normalize_ending_slashes = null
          sources                  = []
          target                   = null
        }]
        user_agent_parser = [{
          is_enabled = null
          is_encoded = null
          name       = null
          sources    = []
          target     = null
        }]
      }]
    }]
    service_remapper = [{
      is_enabled = null
      name       = null
      sources    = []
    }]
    status_remapper = [{
      is_enabled = null
      name       = null
      sources    = []
    }]
    string_builder_processor = [{
      is_enabled         = null
      is_replace_missing = null
      name               = null
      target             = null
      template           = null
    }]
    trace_id_remapper = [{
      is_enabled = null
      name       = null
      sources    = []
    }]
    url_parser = [{
      is_enabled               = null
      name                     = null
      normalize_ending_slashes = null
      sources                  = []
      target                   = null
    }]
    user_agent_parser = [{
      is_enabled = null
      is_encoded = null
      name       = null
      sources    = []
      target     = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      query = string
    }
  ))
}

variable "processor" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      arithmetic_processor = list(object(
        {
          expression         = string
          is_enabled         = bool
          is_replace_missing = bool
          name               = string
          target             = string
        }
      ))
      attribute_remapper = list(object(
        {
          is_enabled           = bool
          name                 = string
          override_on_conflict = bool
          preserve_source      = bool
          source_type          = string
          sources              = list(string)
          target               = string
          target_format        = string
          target_type          = string
        }
      ))
      category_processor = list(object(
        {
          category = list(object(
            {
              filter = list(object(
                {
                  query = string
                }
              ))
              name = string
            }
          ))
          is_enabled = bool
          name       = string
          target     = string
        }
      ))
      date_remapper = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
        }
      ))
      geo_ip_parser = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
          target     = string
        }
      ))
      grok_parser = list(object(
        {
          grok = list(object(
            {
              match_rules   = string
              support_rules = string
            }
          ))
          is_enabled = bool
          name       = string
          samples    = list(string)
          source     = string
        }
      ))
      lookup_processor = list(object(
        {
          default_lookup = string
          is_enabled     = bool
          lookup_table   = list(string)
          name           = string
          source         = string
          target         = string
        }
      ))
      message_remapper = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
        }
      ))
      pipeline = list(object(
        {
          filter = list(object(
            {
              query = string
            }
          ))
          is_enabled = bool
          name       = string
          processor = list(object(
            {
              arithmetic_processor = list(object(
                {
                  expression         = string
                  is_enabled         = bool
                  is_replace_missing = bool
                  name               = string
                  target             = string
                }
              ))
              attribute_remapper = list(object(
                {
                  is_enabled           = bool
                  name                 = string
                  override_on_conflict = bool
                  preserve_source      = bool
                  source_type          = string
                  sources              = list(string)
                  target               = string
                  target_format        = string
                  target_type          = string
                }
              ))
              category_processor = list(object(
                {
                  category = list(object(
                    {
                      filter = list(object(
                        {
                          query = string
                        }
                      ))
                      name = string
                    }
                  ))
                  is_enabled = bool
                  name       = string
                  target     = string
                }
              ))
              date_remapper = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                }
              ))
              geo_ip_parser = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                  target     = string
                }
              ))
              grok_parser = list(object(
                {
                  grok = list(object(
                    {
                      match_rules   = string
                      support_rules = string
                    }
                  ))
                  is_enabled = bool
                  name       = string
                  samples    = list(string)
                  source     = string
                }
              ))
              lookup_processor = list(object(
                {
                  default_lookup = string
                  is_enabled     = bool
                  lookup_table   = list(string)
                  name           = string
                  source         = string
                  target         = string
                }
              ))
              message_remapper = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                }
              ))
              service_remapper = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                }
              ))
              status_remapper = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                }
              ))
              string_builder_processor = list(object(
                {
                  is_enabled         = bool
                  is_replace_missing = bool
                  name               = string
                  target             = string
                  template           = string
                }
              ))
              trace_id_remapper = list(object(
                {
                  is_enabled = bool
                  name       = string
                  sources    = list(string)
                }
              ))
              url_parser = list(object(
                {
                  is_enabled               = bool
                  name                     = string
                  normalize_ending_slashes = bool
                  sources                  = list(string)
                  target                   = string
                }
              ))
              user_agent_parser = list(object(
                {
                  is_enabled = bool
                  is_encoded = bool
                  name       = string
                  sources    = list(string)
                  target     = string
                }
              ))
            }
          ))
        }
      ))
      service_remapper = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
        }
      ))
      status_remapper = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
        }
      ))
      string_builder_processor = list(object(
        {
          is_enabled         = bool
          is_replace_missing = bool
          name               = string
          target             = string
          template           = string
        }
      ))
      trace_id_remapper = list(object(
        {
          is_enabled = bool
          name       = string
          sources    = list(string)
        }
      ))
      url_parser = list(object(
        {
          is_enabled               = bool
          name                     = string
          normalize_ending_slashes = bool
          sources                  = list(string)
          target                   = string
        }
      ))
      user_agent_parser = list(object(
        {
          is_enabled = bool
          is_encoded = bool
          name       = string
          sources    = list(string)
          target     = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_custom_pipeline" "this" {
  is_enabled = var.is_enabled
  name       = var.name

  dynamic "filter" {
    for_each = var.filter
    content {
      query = filter.value["query"]
    }
  }

  dynamic "processor" {
    for_each = var.processor
    content {

      dynamic "arithmetic_processor" {
        for_each = processor.value.arithmetic_processor
        content {
          expression         = arithmetic_processor.value["expression"]
          is_enabled         = arithmetic_processor.value["is_enabled"]
          is_replace_missing = arithmetic_processor.value["is_replace_missing"]
          name               = arithmetic_processor.value["name"]
          target             = arithmetic_processor.value["target"]
        }
      }

      dynamic "attribute_remapper" {
        for_each = processor.value.attribute_remapper
        content {
          is_enabled           = attribute_remapper.value["is_enabled"]
          name                 = attribute_remapper.value["name"]
          override_on_conflict = attribute_remapper.value["override_on_conflict"]
          preserve_source      = attribute_remapper.value["preserve_source"]
          source_type          = attribute_remapper.value["source_type"]
          sources              = attribute_remapper.value["sources"]
          target               = attribute_remapper.value["target"]
          target_format        = attribute_remapper.value["target_format"]
          target_type          = attribute_remapper.value["target_type"]
        }
      }

      dynamic "category_processor" {
        for_each = processor.value.category_processor
        content {
          is_enabled = category_processor.value["is_enabled"]
          name       = category_processor.value["name"]
          target     = category_processor.value["target"]

          dynamic "category" {
            for_each = category_processor.value.category
            content {
              name = category.value["name"]

              dynamic "filter" {
                for_each = category.value.filter
                content {
                  query = filter.value["query"]
                }
              }

            }
          }

        }
      }

      dynamic "date_remapper" {
        for_each = processor.value.date_remapper
        content {
          is_enabled = date_remapper.value["is_enabled"]
          name       = date_remapper.value["name"]
          sources    = date_remapper.value["sources"]
        }
      }

      dynamic "geo_ip_parser" {
        for_each = processor.value.geo_ip_parser
        content {
          is_enabled = geo_ip_parser.value["is_enabled"]
          name       = geo_ip_parser.value["name"]
          sources    = geo_ip_parser.value["sources"]
          target     = geo_ip_parser.value["target"]
        }
      }

      dynamic "grok_parser" {
        for_each = processor.value.grok_parser
        content {
          is_enabled = grok_parser.value["is_enabled"]
          name       = grok_parser.value["name"]
          samples    = grok_parser.value["samples"]
          source     = grok_parser.value["source"]

          dynamic "grok" {
            for_each = grok_parser.value.grok
            content {
              match_rules   = grok.value["match_rules"]
              support_rules = grok.value["support_rules"]
            }
          }

        }
      }

      dynamic "lookup_processor" {
        for_each = processor.value.lookup_processor
        content {
          default_lookup = lookup_processor.value["default_lookup"]
          is_enabled     = lookup_processor.value["is_enabled"]
          lookup_table   = lookup_processor.value["lookup_table"]
          name           = lookup_processor.value["name"]
          source         = lookup_processor.value["source"]
          target         = lookup_processor.value["target"]
        }
      }

      dynamic "message_remapper" {
        for_each = processor.value.message_remapper
        content {
          is_enabled = message_remapper.value["is_enabled"]
          name       = message_remapper.value["name"]
          sources    = message_remapper.value["sources"]
        }
      }

      dynamic "pipeline" {
        for_each = processor.value.pipeline
        content {
          is_enabled = pipeline.value["is_enabled"]
          name       = pipeline.value["name"]

          dynamic "filter" {
            for_each = pipeline.value.filter
            content {
              query = filter.value["query"]
            }
          }

          dynamic "processor" {
            for_each = pipeline.value.processor
            content {

              dynamic "arithmetic_processor" {
                for_each = processor.value.arithmetic_processor
                content {
                  expression         = arithmetic_processor.value["expression"]
                  is_enabled         = arithmetic_processor.value["is_enabled"]
                  is_replace_missing = arithmetic_processor.value["is_replace_missing"]
                  name               = arithmetic_processor.value["name"]
                  target             = arithmetic_processor.value["target"]
                }
              }

              dynamic "attribute_remapper" {
                for_each = processor.value.attribute_remapper
                content {
                  is_enabled           = attribute_remapper.value["is_enabled"]
                  name                 = attribute_remapper.value["name"]
                  override_on_conflict = attribute_remapper.value["override_on_conflict"]
                  preserve_source      = attribute_remapper.value["preserve_source"]
                  source_type          = attribute_remapper.value["source_type"]
                  sources              = attribute_remapper.value["sources"]
                  target               = attribute_remapper.value["target"]
                  target_format        = attribute_remapper.value["target_format"]
                  target_type          = attribute_remapper.value["target_type"]
                }
              }

              dynamic "category_processor" {
                for_each = processor.value.category_processor
                content {
                  is_enabled = category_processor.value["is_enabled"]
                  name       = category_processor.value["name"]
                  target     = category_processor.value["target"]

                  dynamic "category" {
                    for_each = category_processor.value.category
                    content {
                      name = category.value["name"]

                      dynamic "filter" {
                        for_each = category.value.filter
                        content {
                          query = filter.value["query"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "date_remapper" {
                for_each = processor.value.date_remapper
                content {
                  is_enabled = date_remapper.value["is_enabled"]
                  name       = date_remapper.value["name"]
                  sources    = date_remapper.value["sources"]
                }
              }

              dynamic "geo_ip_parser" {
                for_each = processor.value.geo_ip_parser
                content {
                  is_enabled = geo_ip_parser.value["is_enabled"]
                  name       = geo_ip_parser.value["name"]
                  sources    = geo_ip_parser.value["sources"]
                  target     = geo_ip_parser.value["target"]
                }
              }

              dynamic "grok_parser" {
                for_each = processor.value.grok_parser
                content {
                  is_enabled = grok_parser.value["is_enabled"]
                  name       = grok_parser.value["name"]
                  samples    = grok_parser.value["samples"]
                  source     = grok_parser.value["source"]

                  dynamic "grok" {
                    for_each = grok_parser.value.grok
                    content {
                      match_rules   = grok.value["match_rules"]
                      support_rules = grok.value["support_rules"]
                    }
                  }

                }
              }

              dynamic "lookup_processor" {
                for_each = processor.value.lookup_processor
                content {
                  default_lookup = lookup_processor.value["default_lookup"]
                  is_enabled     = lookup_processor.value["is_enabled"]
                  lookup_table   = lookup_processor.value["lookup_table"]
                  name           = lookup_processor.value["name"]
                  source         = lookup_processor.value["source"]
                  target         = lookup_processor.value["target"]
                }
              }

              dynamic "message_remapper" {
                for_each = processor.value.message_remapper
                content {
                  is_enabled = message_remapper.value["is_enabled"]
                  name       = message_remapper.value["name"]
                  sources    = message_remapper.value["sources"]
                }
              }

              dynamic "service_remapper" {
                for_each = processor.value.service_remapper
                content {
                  is_enabled = service_remapper.value["is_enabled"]
                  name       = service_remapper.value["name"]
                  sources    = service_remapper.value["sources"]
                }
              }

              dynamic "status_remapper" {
                for_each = processor.value.status_remapper
                content {
                  is_enabled = status_remapper.value["is_enabled"]
                  name       = status_remapper.value["name"]
                  sources    = status_remapper.value["sources"]
                }
              }

              dynamic "string_builder_processor" {
                for_each = processor.value.string_builder_processor
                content {
                  is_enabled         = string_builder_processor.value["is_enabled"]
                  is_replace_missing = string_builder_processor.value["is_replace_missing"]
                  name               = string_builder_processor.value["name"]
                  target             = string_builder_processor.value["target"]
                  template           = string_builder_processor.value["template"]
                }
              }

              dynamic "trace_id_remapper" {
                for_each = processor.value.trace_id_remapper
                content {
                  is_enabled = trace_id_remapper.value["is_enabled"]
                  name       = trace_id_remapper.value["name"]
                  sources    = trace_id_remapper.value["sources"]
                }
              }

              dynamic "url_parser" {
                for_each = processor.value.url_parser
                content {
                  is_enabled               = url_parser.value["is_enabled"]
                  name                     = url_parser.value["name"]
                  normalize_ending_slashes = url_parser.value["normalize_ending_slashes"]
                  sources                  = url_parser.value["sources"]
                  target                   = url_parser.value["target"]
                }
              }

              dynamic "user_agent_parser" {
                for_each = processor.value.user_agent_parser
                content {
                  is_enabled = user_agent_parser.value["is_enabled"]
                  is_encoded = user_agent_parser.value["is_encoded"]
                  name       = user_agent_parser.value["name"]
                  sources    = user_agent_parser.value["sources"]
                  target     = user_agent_parser.value["target"]
                }
              }

            }
          }

        }
      }

      dynamic "service_remapper" {
        for_each = processor.value.service_remapper
        content {
          is_enabled = service_remapper.value["is_enabled"]
          name       = service_remapper.value["name"]
          sources    = service_remapper.value["sources"]
        }
      }

      dynamic "status_remapper" {
        for_each = processor.value.status_remapper
        content {
          is_enabled = status_remapper.value["is_enabled"]
          name       = status_remapper.value["name"]
          sources    = status_remapper.value["sources"]
        }
      }

      dynamic "string_builder_processor" {
        for_each = processor.value.string_builder_processor
        content {
          is_enabled         = string_builder_processor.value["is_enabled"]
          is_replace_missing = string_builder_processor.value["is_replace_missing"]
          name               = string_builder_processor.value["name"]
          target             = string_builder_processor.value["target"]
          template           = string_builder_processor.value["template"]
        }
      }

      dynamic "trace_id_remapper" {
        for_each = processor.value.trace_id_remapper
        content {
          is_enabled = trace_id_remapper.value["is_enabled"]
          name       = trace_id_remapper.value["name"]
          sources    = trace_id_remapper.value["sources"]
        }
      }

      dynamic "url_parser" {
        for_each = processor.value.url_parser
        content {
          is_enabled               = url_parser.value["is_enabled"]
          name                     = url_parser.value["name"]
          normalize_ending_slashes = url_parser.value["normalize_ending_slashes"]
          sources                  = url_parser.value["sources"]
          target                   = url_parser.value["target"]
        }
      }

      dynamic "user_agent_parser" {
        for_each = processor.value.user_agent_parser
        content {
          is_enabled = user_agent_parser.value["is_enabled"]
          is_encoded = user_agent_parser.value["is_encoded"]
          name       = user_agent_parser.value["name"]
          sources    = user_agent_parser.value["sources"]
          target     = user_agent_parser.value["target"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_custom_pipeline.this.id
}

output "this" {
  value = datadog_logs_custom_pipeline.this
}
```

[top](#index)