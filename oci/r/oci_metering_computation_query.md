# oci_metering_computation_query

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_metering_computation_query" {
  source = "./modules/oci/r/oci_metering_computation_query"

  # compartment_id - (required) is a type of string
  compartment_id = null

  query_definition = [{
    cost_analysis_ui = [{
      graph               = null
      is_cumulative_graph = null
    }]
    display_name = null
    report_query = [{
      compartment_depth = null
      date_range_name   = null
      filter            = null
      granularity       = null
      group_by          = []
      group_by_tag = [{
        key       = null
        namespace = null
        value     = null
      }]
      is_aggregate_by_time = null
      query_type           = null
      tenant_id            = null
      time_usage_ended     = null
      time_usage_started   = null
    }]
    version = null
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

variable "query_definition" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cost_analysis_ui = list(object(
        {
          graph               = string
          is_cumulative_graph = bool
        }
      ))
      display_name = string
      report_query = list(object(
        {
          compartment_depth = number
          date_range_name   = string
          filter            = string
          granularity       = string
          group_by          = list(string)
          group_by_tag = list(object(
            {
              key       = string
              namespace = string
              value     = string
            }
          ))
          is_aggregate_by_time = bool
          query_type           = string
          tenant_id            = string
          time_usage_ended     = string
          time_usage_started   = string
        }
      ))
      version = number
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
resource "oci_metering_computation_query" "this" {
  compartment_id = var.compartment_id

  dynamic "query_definition" {
    for_each = var.query_definition
    content {
      display_name = query_definition.value["display_name"]
      version      = query_definition.value["version"]

      dynamic "cost_analysis_ui" {
        for_each = query_definition.value.cost_analysis_ui
        content {
          graph               = cost_analysis_ui.value["graph"]
          is_cumulative_graph = cost_analysis_ui.value["is_cumulative_graph"]
        }
      }

      dynamic "report_query" {
        for_each = query_definition.value.report_query
        content {
          compartment_depth    = report_query.value["compartment_depth"]
          date_range_name      = report_query.value["date_range_name"]
          filter               = report_query.value["filter"]
          granularity          = report_query.value["granularity"]
          group_by             = report_query.value["group_by"]
          is_aggregate_by_time = report_query.value["is_aggregate_by_time"]
          query_type           = report_query.value["query_type"]
          tenant_id            = report_query.value["tenant_id"]
          time_usage_ended     = report_query.value["time_usage_ended"]
          time_usage_started   = report_query.value["time_usage_started"]

          dynamic "group_by_tag" {
            for_each = report_query.value.group_by_tag
            content {
              key       = group_by_tag.value["key"]
              namespace = group_by_tag.value["namespace"]
              value     = group_by_tag.value["value"]
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
output "id" {
  description = "returns a string"
  value       = oci_metering_computation_query.this.id
}

output "this" {
  value = oci_metering_computation_query.this
}
```

[top](#index)