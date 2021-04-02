# oci_logging_unified_agent_configuration

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_logging_unified_agent_configuration" {
  source = "./modules/oci/r/oci_logging_unified_agent_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_enabled - (required) is a type of bool
  is_enabled = null

  group_association = [{
    group_list = []
  }]

  service_configuration = [{
    configuration_type = null
    destination = [{
      log_object_id = null
    }]
    sources = [{
      channels = []
      name     = null
      parser = [{
        delimiter                  = null
        expression                 = null
        field_time_key             = null
        format                     = []
        format_firstline           = null
        grok_failure_key           = null
        grok_name_key              = null
        is_estimate_current_event  = null
        is_keep_time_key           = null
        is_null_empty_string       = null
        is_support_colonless_ident = null
        is_with_priority           = null
        keys                       = []
        message_format             = null
        message_key                = null
        multi_line_start_regexp    = null
        null_value_pattern         = null
        parser_type                = null
        patterns = [{
          field_time_format = null
          field_time_key    = null
          field_time_zone   = null
          name              = null
          pattern           = null
        }]
        rfc5424time_format      = null
        syslog_parser_type      = null
        time_format             = null
        time_type               = null
        timeout_in_milliseconds = null
        types                   = {}
      }]
      paths       = []
      source_type = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_enabled" {
  description = "(required)"
  type        = bool
}

variable "group_association" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_list = list(string)
    }
  ))
  default = []
}

variable "service_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      configuration_type = string
      destination = list(object(
        {
          log_object_id = string
        }
      ))
      sources = list(object(
        {
          channels = list(string)
          name     = string
          parser = list(object(
            {
              delimiter                  = string
              expression                 = string
              field_time_key             = string
              format                     = list(string)
              format_firstline           = string
              grok_failure_key           = string
              grok_name_key              = string
              is_estimate_current_event  = bool
              is_keep_time_key           = bool
              is_null_empty_string       = bool
              is_support_colonless_ident = bool
              is_with_priority           = bool
              keys                       = list(string)
              message_format             = string
              message_key                = string
              multi_line_start_regexp    = string
              null_value_pattern         = string
              parser_type                = string
              patterns = list(object(
                {
                  field_time_format = string
                  field_time_key    = string
                  field_time_zone   = string
                  name              = string
                  pattern           = string
                }
              ))
              rfc5424time_format      = string
              syslog_parser_type      = string
              time_format             = string
              time_type               = string
              timeout_in_milliseconds = number
              types                   = map(string)
            }
          ))
          paths       = list(string)
          source_type = string
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
resource "oci_logging_unified_agent_configuration" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  is_enabled     = var.is_enabled

  dynamic "group_association" {
    for_each = var.group_association
    content {
      group_list = group_association.value["group_list"]
    }
  }

  dynamic "service_configuration" {
    for_each = var.service_configuration
    content {
      configuration_type = service_configuration.value["configuration_type"]

      dynamic "destination" {
        for_each = service_configuration.value.destination
        content {
          log_object_id = destination.value["log_object_id"]
        }
      }

      dynamic "sources" {
        for_each = service_configuration.value.sources
        content {
          channels    = sources.value["channels"]
          name        = sources.value["name"]
          paths       = sources.value["paths"]
          source_type = sources.value["source_type"]

          dynamic "parser" {
            for_each = sources.value.parser
            content {
              delimiter                  = parser.value["delimiter"]
              expression                 = parser.value["expression"]
              field_time_key             = parser.value["field_time_key"]
              format                     = parser.value["format"]
              format_firstline           = parser.value["format_firstline"]
              grok_failure_key           = parser.value["grok_failure_key"]
              grok_name_key              = parser.value["grok_name_key"]
              is_estimate_current_event  = parser.value["is_estimate_current_event"]
              is_keep_time_key           = parser.value["is_keep_time_key"]
              is_null_empty_string       = parser.value["is_null_empty_string"]
              is_support_colonless_ident = parser.value["is_support_colonless_ident"]
              is_with_priority           = parser.value["is_with_priority"]
              keys                       = parser.value["keys"]
              message_format             = parser.value["message_format"]
              message_key                = parser.value["message_key"]
              multi_line_start_regexp    = parser.value["multi_line_start_regexp"]
              null_value_pattern         = parser.value["null_value_pattern"]
              parser_type                = parser.value["parser_type"]
              rfc5424time_format         = parser.value["rfc5424time_format"]
              syslog_parser_type         = parser.value["syslog_parser_type"]
              time_format                = parser.value["time_format"]
              time_type                  = parser.value["time_type"]
              timeout_in_milliseconds    = parser.value["timeout_in_milliseconds"]
              types                      = parser.value["types"]

              dynamic "patterns" {
                for_each = parser.value.patterns
                content {
                  field_time_format = patterns.value["field_time_format"]
                  field_time_key    = patterns.value["field_time_key"]
                  field_time_zone   = patterns.value["field_time_zone"]
                  name              = patterns.value["name"]
                  pattern           = patterns.value["pattern"]
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
output "configuration_state" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.configuration_state
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_logging_unified_agent_configuration.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_logging_unified_agent_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = oci_logging_unified_agent_configuration.this.time_last_modified
}

output "this" {
  value = oci_logging_unified_agent_configuration.this
}
```

[top](#index)