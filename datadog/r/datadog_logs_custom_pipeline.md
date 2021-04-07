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
    datadog = ">= 2.24.0"
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
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # name - (required) is a type of string
  name = var.name

  dynamic "filter" {
    for_each = var.filter
    content {
      # query - (required) is a type of string
      query = filter.value["query"]
    }
  }

  dynamic "processor" {
    for_each = var.processor
    content {

      dynamic "arithmetic_processor" {
        for_each = processor.value.arithmetic_processor
        content {
          # expression - (required) is a type of string
          expression = arithmetic_processor.value["expression"]
          # is_enabled - (optional) is a type of bool
          is_enabled = arithmetic_processor.value["is_enabled"]
          # is_replace_missing - (optional) is a type of bool
          is_replace_missing = arithmetic_processor.value["is_replace_missing"]
          # name - (optional) is a type of string
          name = arithmetic_processor.value["name"]
          # target - (required) is a type of string
          target = arithmetic_processor.value["target"]
        }
      }

      dynamic "attribute_remapper" {
        for_each = processor.value.attribute_remapper
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = attribute_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = attribute_remapper.value["name"]
          # override_on_conflict - (optional) is a type of bool
          override_on_conflict = attribute_remapper.value["override_on_conflict"]
          # preserve_source - (optional) is a type of bool
          preserve_source = attribute_remapper.value["preserve_source"]
          # source_type - (required) is a type of string
          source_type = attribute_remapper.value["source_type"]
          # sources - (required) is a type of list of string
          sources = attribute_remapper.value["sources"]
          # target - (required) is a type of string
          target = attribute_remapper.value["target"]
          # target_format - (optional) is a type of string
          target_format = attribute_remapper.value["target_format"]
          # target_type - (required) is a type of string
          target_type = attribute_remapper.value["target_type"]
        }
      }

      dynamic "category_processor" {
        for_each = processor.value.category_processor
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = category_processor.value["is_enabled"]
          # name - (optional) is a type of string
          name = category_processor.value["name"]
          # target - (required) is a type of string
          target = category_processor.value["target"]

          dynamic "category" {
            for_each = category_processor.value.category
            content {
              # name - (required) is a type of string
              name = category.value["name"]

              dynamic "filter" {
                for_each = category.value.filter
                content {
                  # query - (required) is a type of string
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
          # is_enabled - (optional) is a type of bool
          is_enabled = date_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = date_remapper.value["name"]
          # sources - (required) is a type of list of string
          sources = date_remapper.value["sources"]
        }
      }

      dynamic "geo_ip_parser" {
        for_each = processor.value.geo_ip_parser
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = geo_ip_parser.value["is_enabled"]
          # name - (optional) is a type of string
          name = geo_ip_parser.value["name"]
          # sources - (required) is a type of list of string
          sources = geo_ip_parser.value["sources"]
          # target - (required) is a type of string
          target = geo_ip_parser.value["target"]
        }
      }

      dynamic "grok_parser" {
        for_each = processor.value.grok_parser
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = grok_parser.value["is_enabled"]
          # name - (optional) is a type of string
          name = grok_parser.value["name"]
          # samples - (optional) is a type of list of string
          samples = grok_parser.value["samples"]
          # source - (required) is a type of string
          source = grok_parser.value["source"]

          dynamic "grok" {
            for_each = grok_parser.value.grok
            content {
              # match_rules - (required) is a type of string
              match_rules = grok.value["match_rules"]
              # support_rules - (required) is a type of string
              support_rules = grok.value["support_rules"]
            }
          }

        }
      }

      dynamic "lookup_processor" {
        for_each = processor.value.lookup_processor
        content {
          # default_lookup - (optional) is a type of string
          default_lookup = lookup_processor.value["default_lookup"]
          # is_enabled - (optional) is a type of bool
          is_enabled = lookup_processor.value["is_enabled"]
          # lookup_table - (required) is a type of list of string
          lookup_table = lookup_processor.value["lookup_table"]
          # name - (optional) is a type of string
          name = lookup_processor.value["name"]
          # source - (required) is a type of string
          source = lookup_processor.value["source"]
          # target - (required) is a type of string
          target = lookup_processor.value["target"]
        }
      }

      dynamic "message_remapper" {
        for_each = processor.value.message_remapper
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = message_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = message_remapper.value["name"]
          # sources - (required) is a type of list of string
          sources = message_remapper.value["sources"]
        }
      }

      dynamic "pipeline" {
        for_each = processor.value.pipeline
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = pipeline.value["is_enabled"]
          # name - (required) is a type of string
          name = pipeline.value["name"]

          dynamic "filter" {
            for_each = pipeline.value.filter
            content {
              # query - (required) is a type of string
              query = filter.value["query"]
            }
          }

          dynamic "processor" {
            for_each = pipeline.value.processor
            content {

              dynamic "arithmetic_processor" {
                for_each = processor.value.arithmetic_processor
                content {
                  # expression - (required) is a type of string
                  expression = arithmetic_processor.value["expression"]
                  # is_enabled - (optional) is a type of bool
                  is_enabled = arithmetic_processor.value["is_enabled"]
                  # is_replace_missing - (optional) is a type of bool
                  is_replace_missing = arithmetic_processor.value["is_replace_missing"]
                  # name - (optional) is a type of string
                  name = arithmetic_processor.value["name"]
                  # target - (required) is a type of string
                  target = arithmetic_processor.value["target"]
                }
              }

              dynamic "attribute_remapper" {
                for_each = processor.value.attribute_remapper
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = attribute_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = attribute_remapper.value["name"]
                  # override_on_conflict - (optional) is a type of bool
                  override_on_conflict = attribute_remapper.value["override_on_conflict"]
                  # preserve_source - (optional) is a type of bool
                  preserve_source = attribute_remapper.value["preserve_source"]
                  # source_type - (required) is a type of string
                  source_type = attribute_remapper.value["source_type"]
                  # sources - (required) is a type of list of string
                  sources = attribute_remapper.value["sources"]
                  # target - (required) is a type of string
                  target = attribute_remapper.value["target"]
                  # target_format - (optional) is a type of string
                  target_format = attribute_remapper.value["target_format"]
                  # target_type - (required) is a type of string
                  target_type = attribute_remapper.value["target_type"]
                }
              }

              dynamic "category_processor" {
                for_each = processor.value.category_processor
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = category_processor.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = category_processor.value["name"]
                  # target - (required) is a type of string
                  target = category_processor.value["target"]

                  dynamic "category" {
                    for_each = category_processor.value.category
                    content {
                      # name - (required) is a type of string
                      name = category.value["name"]

                      dynamic "filter" {
                        for_each = category.value.filter
                        content {
                          # query - (required) is a type of string
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
                  # is_enabled - (optional) is a type of bool
                  is_enabled = date_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = date_remapper.value["name"]
                  # sources - (required) is a type of list of string
                  sources = date_remapper.value["sources"]
                }
              }

              dynamic "geo_ip_parser" {
                for_each = processor.value.geo_ip_parser
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = geo_ip_parser.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = geo_ip_parser.value["name"]
                  # sources - (required) is a type of list of string
                  sources = geo_ip_parser.value["sources"]
                  # target - (required) is a type of string
                  target = geo_ip_parser.value["target"]
                }
              }

              dynamic "grok_parser" {
                for_each = processor.value.grok_parser
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = grok_parser.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = grok_parser.value["name"]
                  # samples - (optional) is a type of list of string
                  samples = grok_parser.value["samples"]
                  # source - (required) is a type of string
                  source = grok_parser.value["source"]

                  dynamic "grok" {
                    for_each = grok_parser.value.grok
                    content {
                      # match_rules - (required) is a type of string
                      match_rules = grok.value["match_rules"]
                      # support_rules - (required) is a type of string
                      support_rules = grok.value["support_rules"]
                    }
                  }

                }
              }

              dynamic "lookup_processor" {
                for_each = processor.value.lookup_processor
                content {
                  # default_lookup - (optional) is a type of string
                  default_lookup = lookup_processor.value["default_lookup"]
                  # is_enabled - (optional) is a type of bool
                  is_enabled = lookup_processor.value["is_enabled"]
                  # lookup_table - (required) is a type of list of string
                  lookup_table = lookup_processor.value["lookup_table"]
                  # name - (optional) is a type of string
                  name = lookup_processor.value["name"]
                  # source - (required) is a type of string
                  source = lookup_processor.value["source"]
                  # target - (required) is a type of string
                  target = lookup_processor.value["target"]
                }
              }

              dynamic "message_remapper" {
                for_each = processor.value.message_remapper
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = message_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = message_remapper.value["name"]
                  # sources - (required) is a type of list of string
                  sources = message_remapper.value["sources"]
                }
              }

              dynamic "service_remapper" {
                for_each = processor.value.service_remapper
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = service_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = service_remapper.value["name"]
                  # sources - (required) is a type of list of string
                  sources = service_remapper.value["sources"]
                }
              }

              dynamic "status_remapper" {
                for_each = processor.value.status_remapper
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = status_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = status_remapper.value["name"]
                  # sources - (required) is a type of list of string
                  sources = status_remapper.value["sources"]
                }
              }

              dynamic "string_builder_processor" {
                for_each = processor.value.string_builder_processor
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = string_builder_processor.value["is_enabled"]
                  # is_replace_missing - (optional) is a type of bool
                  is_replace_missing = string_builder_processor.value["is_replace_missing"]
                  # name - (optional) is a type of string
                  name = string_builder_processor.value["name"]
                  # target - (required) is a type of string
                  target = string_builder_processor.value["target"]
                  # template - (required) is a type of string
                  template = string_builder_processor.value["template"]
                }
              }

              dynamic "trace_id_remapper" {
                for_each = processor.value.trace_id_remapper
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = trace_id_remapper.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = trace_id_remapper.value["name"]
                  # sources - (required) is a type of list of string
                  sources = trace_id_remapper.value["sources"]
                }
              }

              dynamic "url_parser" {
                for_each = processor.value.url_parser
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = url_parser.value["is_enabled"]
                  # name - (optional) is a type of string
                  name = url_parser.value["name"]
                  # normalize_ending_slashes - (optional) is a type of bool
                  normalize_ending_slashes = url_parser.value["normalize_ending_slashes"]
                  # sources - (required) is a type of list of string
                  sources = url_parser.value["sources"]
                  # target - (required) is a type of string
                  target = url_parser.value["target"]
                }
              }

              dynamic "user_agent_parser" {
                for_each = processor.value.user_agent_parser
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = user_agent_parser.value["is_enabled"]
                  # is_encoded - (optional) is a type of bool
                  is_encoded = user_agent_parser.value["is_encoded"]
                  # name - (optional) is a type of string
                  name = user_agent_parser.value["name"]
                  # sources - (required) is a type of list of string
                  sources = user_agent_parser.value["sources"]
                  # target - (required) is a type of string
                  target = user_agent_parser.value["target"]
                }
              }

            }
          }

        }
      }

      dynamic "service_remapper" {
        for_each = processor.value.service_remapper
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = service_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = service_remapper.value["name"]
          # sources - (required) is a type of list of string
          sources = service_remapper.value["sources"]
        }
      }

      dynamic "status_remapper" {
        for_each = processor.value.status_remapper
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = status_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = status_remapper.value["name"]
          # sources - (required) is a type of list of string
          sources = status_remapper.value["sources"]
        }
      }

      dynamic "string_builder_processor" {
        for_each = processor.value.string_builder_processor
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = string_builder_processor.value["is_enabled"]
          # is_replace_missing - (optional) is a type of bool
          is_replace_missing = string_builder_processor.value["is_replace_missing"]
          # name - (optional) is a type of string
          name = string_builder_processor.value["name"]
          # target - (required) is a type of string
          target = string_builder_processor.value["target"]
          # template - (required) is a type of string
          template = string_builder_processor.value["template"]
        }
      }

      dynamic "trace_id_remapper" {
        for_each = processor.value.trace_id_remapper
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = trace_id_remapper.value["is_enabled"]
          # name - (optional) is a type of string
          name = trace_id_remapper.value["name"]
          # sources - (required) is a type of list of string
          sources = trace_id_remapper.value["sources"]
        }
      }

      dynamic "url_parser" {
        for_each = processor.value.url_parser
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = url_parser.value["is_enabled"]
          # name - (optional) is a type of string
          name = url_parser.value["name"]
          # normalize_ending_slashes - (optional) is a type of bool
          normalize_ending_slashes = url_parser.value["normalize_ending_slashes"]
          # sources - (required) is a type of list of string
          sources = url_parser.value["sources"]
          # target - (required) is a type of string
          target = url_parser.value["target"]
        }
      }

      dynamic "user_agent_parser" {
        for_each = processor.value.user_agent_parser
        content {
          # is_enabled - (optional) is a type of bool
          is_enabled = user_agent_parser.value["is_enabled"]
          # is_encoded - (optional) is a type of bool
          is_encoded = user_agent_parser.value["is_encoded"]
          # name - (optional) is a type of string
          name = user_agent_parser.value["name"]
          # sources - (required) is a type of list of string
          sources = user_agent_parser.value["sources"]
          # target - (required) is a type of string
          target = user_agent_parser.value["target"]
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