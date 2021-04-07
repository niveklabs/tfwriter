# circonus_dashboard

[back](../circonus.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    circonus = ">= 0.12.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "circonus_dashboard" {
  source = "./modules/circonus/r/circonus_dashboard"

  # account_default - (optional) is a type of bool
  account_default = null
  # grid_layout - (required) is a type of map of number
  grid_layout = {}
  # shared - (optional) is a type of bool
  shared = null
  # title - (required) is a type of string
  title = null

  options = [{
    access_configs = [{
      black_dash             = null
      enabled                = null
      full_screen            = null
      full_screen_hide_title = null
      nick_name              = null
      scale_text             = null
      shared_id              = null
      text_size              = null
    }]
    full_screen_hide_title = null
    hide_grid              = null
    scale_text             = null
    text_size              = null
  }]

  widget = [{
    active = null
    height = null
    name   = null
    origin = null
    settings = [{
      account_id   = null
      acknowledged = null
      algorithm    = null
      autoformat   = null
      bad_rules = [{
        color     = null
        criterion = null
        value     = null
      }]
      body_format  = null
      caql         = null
      chart_type   = null
      check_uuid   = null
      cleared      = null
      cluster_id   = null
      cluster_name = null
      content_type = null
      datapoints = [{
        _check_id    = null
        _metric_type = null
        label        = null
        metric       = null
      }]
      date_window         = null
      dependents          = null
      disable_autoformat  = null
      display             = null
      display_markup      = null
      format              = null
      formula             = null
      good_color          = null
      graph_uuid          = null
      hide_xaxis          = null
      hide_yaxis          = null
      key_inline          = null
      key_loc             = null
      key_size            = null
      key_wrap            = null
      label               = null
      layout              = null
      layout_style        = null
      limit               = null
      link_url            = null
      maintenance         = null
      markup              = null
      metric_display_name = null
      metric_name         = null
      metric_type         = null
      min_age             = null
      overlay_set_id      = null
      period              = null
      range_high          = null
      range_low           = null
      real_time           = null
      resource_limit      = null
      resource_usage      = null
      search              = null
      severity            = null
      show_flags          = null
      show_value          = null
      size                = null
      text_align          = null
      threshold           = null
      thresholds = [{
        colors = []
        flip   = null
        values = []
      }]
      time_window  = null
      title        = null
      title_format = null
      trend        = null
      type         = null
      use_default  = null
      value_type   = null
    }]
    type      = null
    widget_id = null
    width     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "grid_layout" {
  description = "(required)"
  type        = map(number)
}

variable "shared" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "title" {
  description = "(required) - The title of the dashboard."
  type        = string
}

variable "options" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      access_configs = set(object(
        {
          black_dash             = bool
          enabled                = bool
          full_screen            = bool
          full_screen_hide_title = bool
          nick_name              = string
          scale_text             = bool
          shared_id              = string
          text_size              = number
        }
      ))
      full_screen_hide_title = bool
      hide_grid              = bool
      scale_text             = bool
      text_size              = number
    }
  ))
}

variable "widget" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      active = bool
      height = number
      name   = string
      origin = string
      settings = set(object(
        {
          account_id   = string
          acknowledged = string
          algorithm    = string
          autoformat   = bool
          bad_rules = list(object(
            {
              color     = string
              criterion = string
              value     = string
            }
          ))
          body_format  = string
          caql         = string
          chart_type   = string
          check_uuid   = string
          cleared      = string
          cluster_id   = number
          cluster_name = string
          content_type = string
          datapoints = set(object(
            {
              _check_id    = number
              _metric_type = string
              label        = string
              metric       = string
            }
          ))
          date_window         = string
          dependents          = string
          disable_autoformat  = bool
          display             = string
          display_markup      = string
          format              = string
          formula             = string
          good_color          = string
          graph_uuid          = string
          hide_xaxis          = bool
          hide_yaxis          = bool
          key_inline          = bool
          key_loc             = string
          key_size            = number
          key_wrap            = bool
          label               = string
          layout              = string
          layout_style        = string
          limit               = number
          link_url            = string
          maintenance         = string
          markup              = string
          metric_display_name = string
          metric_name         = string
          metric_type         = string
          min_age             = string
          overlay_set_id      = string
          period              = number
          range_high          = number
          range_low           = number
          real_time           = bool
          resource_limit      = string
          resource_usage      = string
          search              = string
          severity            = string
          show_flags          = bool
          show_value          = bool
          size                = string
          text_align          = string
          threshold           = number
          thresholds = set(object(
            {
              colors = list(string)
              flip   = bool
              values = list(string)
            }
          ))
          time_window  = string
          title        = string
          title_format = string
          trend        = string
          type         = string
          use_default  = bool
          value_type   = string
        }
      ))
      type      = string
      widget_id = string
      width     = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "circonus_dashboard" "this" {
  # account_default - (optional) is a type of bool
  account_default = var.account_default
  # grid_layout - (required) is a type of map of number
  grid_layout = var.grid_layout
  # shared - (optional) is a type of bool
  shared = var.shared
  # title - (required) is a type of string
  title = var.title

  dynamic "options" {
    for_each = var.options
    content {
      # full_screen_hide_title - (optional) is a type of bool
      full_screen_hide_title = options.value["full_screen_hide_title"]
      # hide_grid - (optional) is a type of bool
      hide_grid = options.value["hide_grid"]
      # scale_text - (optional) is a type of bool
      scale_text = options.value["scale_text"]
      # text_size - (optional) is a type of number
      text_size = options.value["text_size"]

      dynamic "access_configs" {
        for_each = options.value.access_configs
        content {
          # black_dash - (optional) is a type of bool
          black_dash = access_configs.value["black_dash"]
          # enabled - (optional) is a type of bool
          enabled = access_configs.value["enabled"]
          # full_screen - (optional) is a type of bool
          full_screen = access_configs.value["full_screen"]
          # full_screen_hide_title - (optional) is a type of bool
          full_screen_hide_title = access_configs.value["full_screen_hide_title"]
          # nick_name - (optional) is a type of string
          nick_name = access_configs.value["nick_name"]
          # scale_text - (optional) is a type of bool
          scale_text = access_configs.value["scale_text"]
          # shared_id - (optional) is a type of string
          shared_id = access_configs.value["shared_id"]
          # text_size - (optional) is a type of number
          text_size = access_configs.value["text_size"]
        }
      }

    }
  }

  dynamic "widget" {
    for_each = var.widget
    content {
      # active - (optional) is a type of bool
      active = widget.value["active"]
      # height - (required) is a type of number
      height = widget.value["height"]
      # name - (required) is a type of string
      name = widget.value["name"]
      # origin - (required) is a type of string
      origin = widget.value["origin"]
      # type - (required) is a type of string
      type = widget.value["type"]
      # widget_id - (required) is a type of string
      widget_id = widget.value["widget_id"]
      # width - (required) is a type of number
      width = widget.value["width"]

      dynamic "settings" {
        for_each = widget.value.settings
        content {
          # account_id - (optional) is a type of string
          account_id = settings.value["account_id"]
          # acknowledged - (optional) is a type of string
          acknowledged = settings.value["acknowledged"]
          # algorithm - (optional) is a type of string
          algorithm = settings.value["algorithm"]
          # autoformat - (optional) is a type of bool
          autoformat = settings.value["autoformat"]
          # body_format - (optional) is a type of string
          body_format = settings.value["body_format"]
          # caql - (optional) is a type of string
          caql = settings.value["caql"]
          # chart_type - (optional) is a type of string
          chart_type = settings.value["chart_type"]
          # check_uuid - (optional) is a type of string
          check_uuid = settings.value["check_uuid"]
          # cleared - (optional) is a type of string
          cleared = settings.value["cleared"]
          # cluster_id - (optional) is a type of number
          cluster_id = settings.value["cluster_id"]
          # cluster_name - (optional) is a type of string
          cluster_name = settings.value["cluster_name"]
          # content_type - (optional) is a type of string
          content_type = settings.value["content_type"]
          # date_window - (optional) is a type of string
          date_window = settings.value["date_window"]
          # dependents - (optional) is a type of string
          dependents = settings.value["dependents"]
          # disable_autoformat - (optional) is a type of bool
          disable_autoformat = settings.value["disable_autoformat"]
          # display - (optional) is a type of string
          display = settings.value["display"]
          # display_markup - (optional) is a type of string
          display_markup = settings.value["display_markup"]
          # format - (optional) is a type of string
          format = settings.value["format"]
          # formula - (optional) is a type of string
          formula = settings.value["formula"]
          # good_color - (optional) is a type of string
          good_color = settings.value["good_color"]
          # graph_uuid - (optional) is a type of string
          graph_uuid = settings.value["graph_uuid"]
          # hide_xaxis - (optional) is a type of bool
          hide_xaxis = settings.value["hide_xaxis"]
          # hide_yaxis - (optional) is a type of bool
          hide_yaxis = settings.value["hide_yaxis"]
          # key_inline - (optional) is a type of bool
          key_inline = settings.value["key_inline"]
          # key_loc - (optional) is a type of string
          key_loc = settings.value["key_loc"]
          # key_size - (optional) is a type of number
          key_size = settings.value["key_size"]
          # key_wrap - (optional) is a type of bool
          key_wrap = settings.value["key_wrap"]
          # label - (optional) is a type of string
          label = settings.value["label"]
          # layout - (optional) is a type of string
          layout = settings.value["layout"]
          # layout_style - (optional) is a type of string
          layout_style = settings.value["layout_style"]
          # limit - (optional) is a type of number
          limit = settings.value["limit"]
          # link_url - (optional) is a type of string
          link_url = settings.value["link_url"]
          # maintenance - (optional) is a type of string
          maintenance = settings.value["maintenance"]
          # markup - (optional) is a type of string
          markup = settings.value["markup"]
          # metric_display_name - (optional) is a type of string
          metric_display_name = settings.value["metric_display_name"]
          # metric_name - (optional) is a type of string
          metric_name = settings.value["metric_name"]
          # metric_type - (optional) is a type of string
          metric_type = settings.value["metric_type"]
          # min_age - (optional) is a type of string
          min_age = settings.value["min_age"]
          # overlay_set_id - (optional) is a type of string
          overlay_set_id = settings.value["overlay_set_id"]
          # period - (optional) is a type of number
          period = settings.value["period"]
          # range_high - (optional) is a type of number
          range_high = settings.value["range_high"]
          # range_low - (optional) is a type of number
          range_low = settings.value["range_low"]
          # real_time - (optional) is a type of bool
          real_time = settings.value["real_time"]
          # resource_limit - (optional) is a type of string
          resource_limit = settings.value["resource_limit"]
          # resource_usage - (optional) is a type of string
          resource_usage = settings.value["resource_usage"]
          # search - (optional) is a type of string
          search = settings.value["search"]
          # severity - (optional) is a type of string
          severity = settings.value["severity"]
          # show_flags - (optional) is a type of bool
          show_flags = settings.value["show_flags"]
          # show_value - (optional) is a type of bool
          show_value = settings.value["show_value"]
          # size - (optional) is a type of string
          size = settings.value["size"]
          # text_align - (optional) is a type of string
          text_align = settings.value["text_align"]
          # threshold - (optional) is a type of number
          threshold = settings.value["threshold"]
          # time_window - (optional) is a type of string
          time_window = settings.value["time_window"]
          # title - (optional) is a type of string
          title = settings.value["title"]
          # title_format - (optional) is a type of string
          title_format = settings.value["title_format"]
          # trend - (optional) is a type of string
          trend = settings.value["trend"]
          # type - (optional) is a type of string
          type = settings.value["type"]
          # use_default - (optional) is a type of bool
          use_default = settings.value["use_default"]
          # value_type - (optional) is a type of string
          value_type = settings.value["value_type"]

          dynamic "bad_rules" {
            for_each = settings.value.bad_rules
            content {
              # color - (required) is a type of string
              color = bad_rules.value["color"]
              # criterion - (required) is a type of string
              criterion = bad_rules.value["criterion"]
              # value - (required) is a type of string
              value = bad_rules.value["value"]
            }
          }

          dynamic "datapoints" {
            for_each = settings.value.datapoints
            content {
              # _check_id - (required) is a type of number
              _check_id = datapoints.value["_check_id"]
              # _metric_type - (required) is a type of string
              _metric_type = datapoints.value["_metric_type"]
              # label - (required) is a type of string
              label = datapoints.value["label"]
              # metric - (required) is a type of string
              metric = datapoints.value["metric"]
            }
          }

          dynamic "thresholds" {
            for_each = settings.value.thresholds
            content {
              # colors - (required) is a type of list of string
              colors = thresholds.value["colors"]
              # flip - (required) is a type of bool
              flip = thresholds.value["flip"]
              # values - (required) is a type of list of string
              values = thresholds.value["values"]
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
output "id" {
  description = "returns a string"
  value       = circonus_dashboard.this.id
}

output "uuid" {
  description = "returns a string"
  value       = circonus_dashboard.this.uuid
}

output "this" {
  value = circonus_dashboard.this
}
```

[top](#index)