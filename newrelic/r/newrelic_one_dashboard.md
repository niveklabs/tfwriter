# newrelic_one_dashboard

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_one_dashboard" {
  source = "./modules/newrelic/r/newrelic_one_dashboard"

  # account_id - (optional) is a type of number
  account_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of string
  permissions = null

  page = [{
    description = null
    guid        = null
    name        = null
    widget_area = [{
      column = null
      height = null
      id     = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_bar = [{
      column              = null
      height              = null
      id                  = null
      linked_entity_guids = []
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_billboard = [{
      column   = null
      critical = null
      height   = null
      id       = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row     = null
      title   = null
      warning = null
      width   = null
    }]
    widget_bullet = [{
      column = null
      height = null
      id     = null
      limit  = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_funnel = [{
      column = null
      height = null
      id     = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_heatmap = [{
      column = null
      height = null
      id     = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_histogram = [{
      column = null
      height = null
      id     = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_line = [{
      column = null
      height = null
      id     = null
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_markdown = [{
      column = null
      height = null
      id     = null
      row    = null
      text   = null
      title  = null
      width  = null
    }]
    widget_pie = [{
      column              = null
      height              = null
      id                  = null
      linked_entity_guids = []
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
    widget_table = [{
      column              = null
      height              = null
      id                  = null
      linked_entity_guids = []
      nrql_query = [{
        account_id = null
        query      = null
      }]
      row   = null
      title = null
      width = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The New Relic account ID where you want to create the dashboard."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The dashboard's description."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The dashboard's name."
  type        = string
}

variable "permissions" {
  description = "(optional) - Determines who can see or edit the dashboard. Valid values are private, public_read_only, public_read_write. Defaults to public_read_only."
  type        = string
  default     = null
}

variable "page" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      description = string
      guid        = string
      name        = string
      widget_area = list(object(
        {
          column = number
          height = number
          id     = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_bar = list(object(
        {
          column              = number
          height              = number
          id                  = string
          linked_entity_guids = list(string)
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_billboard = list(object(
        {
          column   = number
          critical = number
          height   = number
          id       = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row     = number
          title   = string
          warning = number
          width   = number
        }
      ))
      widget_bullet = list(object(
        {
          column = number
          height = number
          id     = string
          limit  = number
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_funnel = list(object(
        {
          column = number
          height = number
          id     = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_heatmap = list(object(
        {
          column = number
          height = number
          id     = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_histogram = list(object(
        {
          column = number
          height = number
          id     = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_line = list(object(
        {
          column = number
          height = number
          id     = string
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_markdown = list(object(
        {
          column = number
          height = number
          id     = string
          row    = number
          text   = string
          title  = string
          width  = number
        }
      ))
      widget_pie = list(object(
        {
          column              = number
          height              = number
          id                  = string
          linked_entity_guids = list(string)
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
      widget_table = list(object(
        {
          column              = number
          height              = number
          id                  = string
          linked_entity_guids = list(string)
          nrql_query = list(object(
            {
              account_id = number
              query      = string
            }
          ))
          row   = number
          title = string
          width = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_one_dashboard" "this" {
  # account_id - (optional) is a type of number
  account_id = var.account_id
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # permissions - (optional) is a type of string
  permissions = var.permissions

  dynamic "page" {
    for_each = var.page
    content {
      # description - (optional) is a type of string
      description = page.value["description"]
      # name - (required) is a type of string
      name = page.value["name"]

      dynamic "widget_area" {
        for_each = page.value.widget_area
        content {
          # column - (required) is a type of number
          column = widget_area.value["column"]
          # height - (optional) is a type of number
          height = widget_area.value["height"]
          # row - (required) is a type of number
          row = widget_area.value["row"]
          # title - (required) is a type of string
          title = widget_area.value["title"]
          # width - (optional) is a type of number
          width = widget_area.value["width"]

          dynamic "nrql_query" {
            for_each = widget_area.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_bar" {
        for_each = page.value.widget_bar
        content {
          # column - (required) is a type of number
          column = widget_bar.value["column"]
          # height - (optional) is a type of number
          height = widget_bar.value["height"]
          # linked_entity_guids - (optional) is a type of list of string
          linked_entity_guids = widget_bar.value["linked_entity_guids"]
          # row - (required) is a type of number
          row = widget_bar.value["row"]
          # title - (required) is a type of string
          title = widget_bar.value["title"]
          # width - (optional) is a type of number
          width = widget_bar.value["width"]

          dynamic "nrql_query" {
            for_each = widget_bar.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_billboard" {
        for_each = page.value.widget_billboard
        content {
          # column - (required) is a type of number
          column = widget_billboard.value["column"]
          # critical - (optional) is a type of number
          critical = widget_billboard.value["critical"]
          # height - (optional) is a type of number
          height = widget_billboard.value["height"]
          # row - (required) is a type of number
          row = widget_billboard.value["row"]
          # title - (required) is a type of string
          title = widget_billboard.value["title"]
          # warning - (optional) is a type of number
          warning = widget_billboard.value["warning"]
          # width - (optional) is a type of number
          width = widget_billboard.value["width"]

          dynamic "nrql_query" {
            for_each = widget_billboard.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_bullet" {
        for_each = page.value.widget_bullet
        content {
          # column - (required) is a type of number
          column = widget_bullet.value["column"]
          # height - (optional) is a type of number
          height = widget_bullet.value["height"]
          # limit - (optional) is a type of number
          limit = widget_bullet.value["limit"]
          # row - (required) is a type of number
          row = widget_bullet.value["row"]
          # title - (required) is a type of string
          title = widget_bullet.value["title"]
          # width - (optional) is a type of number
          width = widget_bullet.value["width"]

          dynamic "nrql_query" {
            for_each = widget_bullet.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_funnel" {
        for_each = page.value.widget_funnel
        content {
          # column - (required) is a type of number
          column = widget_funnel.value["column"]
          # height - (optional) is a type of number
          height = widget_funnel.value["height"]
          # row - (required) is a type of number
          row = widget_funnel.value["row"]
          # title - (required) is a type of string
          title = widget_funnel.value["title"]
          # width - (optional) is a type of number
          width = widget_funnel.value["width"]

          dynamic "nrql_query" {
            for_each = widget_funnel.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_heatmap" {
        for_each = page.value.widget_heatmap
        content {
          # column - (required) is a type of number
          column = widget_heatmap.value["column"]
          # height - (optional) is a type of number
          height = widget_heatmap.value["height"]
          # row - (required) is a type of number
          row = widget_heatmap.value["row"]
          # title - (required) is a type of string
          title = widget_heatmap.value["title"]
          # width - (optional) is a type of number
          width = widget_heatmap.value["width"]

          dynamic "nrql_query" {
            for_each = widget_heatmap.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_histogram" {
        for_each = page.value.widget_histogram
        content {
          # column - (required) is a type of number
          column = widget_histogram.value["column"]
          # height - (optional) is a type of number
          height = widget_histogram.value["height"]
          # row - (required) is a type of number
          row = widget_histogram.value["row"]
          # title - (required) is a type of string
          title = widget_histogram.value["title"]
          # width - (optional) is a type of number
          width = widget_histogram.value["width"]

          dynamic "nrql_query" {
            for_each = widget_histogram.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_line" {
        for_each = page.value.widget_line
        content {
          # column - (required) is a type of number
          column = widget_line.value["column"]
          # height - (optional) is a type of number
          height = widget_line.value["height"]
          # row - (required) is a type of number
          row = widget_line.value["row"]
          # title - (required) is a type of string
          title = widget_line.value["title"]
          # width - (optional) is a type of number
          width = widget_line.value["width"]

          dynamic "nrql_query" {
            for_each = widget_line.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_markdown" {
        for_each = page.value.widget_markdown
        content {
          # column - (required) is a type of number
          column = widget_markdown.value["column"]
          # height - (optional) is a type of number
          height = widget_markdown.value["height"]
          # row - (required) is a type of number
          row = widget_markdown.value["row"]
          # text - (optional) is a type of string
          text = widget_markdown.value["text"]
          # title - (required) is a type of string
          title = widget_markdown.value["title"]
          # width - (optional) is a type of number
          width = widget_markdown.value["width"]
        }
      }

      dynamic "widget_pie" {
        for_each = page.value.widget_pie
        content {
          # column - (required) is a type of number
          column = widget_pie.value["column"]
          # height - (optional) is a type of number
          height = widget_pie.value["height"]
          # linked_entity_guids - (optional) is a type of list of string
          linked_entity_guids = widget_pie.value["linked_entity_guids"]
          # row - (required) is a type of number
          row = widget_pie.value["row"]
          # title - (required) is a type of string
          title = widget_pie.value["title"]
          # width - (optional) is a type of number
          width = widget_pie.value["width"]

          dynamic "nrql_query" {
            for_each = widget_pie.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

      dynamic "widget_table" {
        for_each = page.value.widget_table
        content {
          # column - (required) is a type of number
          column = widget_table.value["column"]
          # height - (optional) is a type of number
          height = widget_table.value["height"]
          # linked_entity_guids - (optional) is a type of list of string
          linked_entity_guids = widget_table.value["linked_entity_guids"]
          # row - (required) is a type of number
          row = widget_table.value["row"]
          # title - (required) is a type of string
          title = widget_table.value["title"]
          # width - (optional) is a type of number
          width = widget_table.value["width"]

          dynamic "nrql_query" {
            for_each = widget_table.value.nrql_query
            content {
              # account_id - (optional) is a type of number
              account_id = nrql_query.value["account_id"]
              # query - (required) is a type of string
              query = nrql_query.value["query"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = newrelic_one_dashboard.this.account_id
}

output "guid" {
  description = "returns a string"
  value       = newrelic_one_dashboard.this.guid
}

output "id" {
  description = "returns a string"
  value       = newrelic_one_dashboard.this.id
}

output "permalink" {
  description = "returns a string"
  value       = newrelic_one_dashboard.this.permalink
}

output "this" {
  value = newrelic_one_dashboard.this
}
```

[top](#index)