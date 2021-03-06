# datadog_dashboard

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
module "datadog_dashboard" {
  source = "./modules/datadog/r/datadog_dashboard"

  # dashboard_lists - (optional) is a type of set of number
  dashboard_lists = []
  # description - (optional) is a type of string
  description = null
  # is_read_only - (optional) is a type of bool
  is_read_only = null
  # layout_type - (required) is a type of string
  layout_type = null
  # notify_list - (optional) is a type of list of string
  notify_list = []
  # title - (required) is a type of string
  title = null
  # url - (optional) is a type of string
  url = null

  template_variable = [{
    default = null
    name    = null
    prefix  = null
  }]

  template_variable_preset = [{
    name = null
    template_variable = [{
      name  = null
      value = null
    }]
  }]

  widget = [{
    alert_graph_definition = [{
      alert_id    = null
      live_span   = null
      time        = {}
      title       = null
      title_align = null
      title_size  = null
      viz_type    = null
    }]
    alert_value_definition = [{
      alert_id    = null
      precision   = null
      text_align  = null
      title       = null
      title_align = null
      title_size  = null
      unit        = null
    }]
    change_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      live_span = null
      request = [{
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        change_type   = null
        compare_to    = null
        increase_good = null
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        order_by  = null
        order_dir = null
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        show_present = null
      }]
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    check_status_definition = [{
      check       = null
      group       = null
      group_by    = []
      grouping    = null
      live_span   = null
      tags        = []
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    distribution_definition = [{
      legend_size = null
      live_span   = null
      request = [{
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        style = [{
          palette = null
        }]
      }]
      show_legend = null
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    event_stream_definition = [{
      event_size     = null
      live_span      = null
      query          = null
      tags_execution = null
      time           = {}
      title          = null
      title_align    = null
      title_size     = null
    }]
    event_timeline_definition = [{
      live_span      = null
      query          = null
      tags_execution = null
      time           = {}
      title          = null
      title_align    = null
      title_size     = null
    }]
    free_text_definition = [{
      color      = null
      font_size  = null
      text       = null
      text_align = null
    }]
    geomap_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      live_span = null
      request = [{
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
      }]
      style = [{
        palette      = null
        palette_flip = null
      }]
      title       = null
      title_align = null
      title_size  = null
      view = [{
        focus = null
      }]
    }]
    group_definition = [{
      layout_type = null
      title       = null
      widget = [{
        alert_graph_definition = [{
          alert_id    = null
          live_span   = null
          time        = {}
          title       = null
          title_align = null
          title_size  = null
          viz_type    = null
        }]
        alert_value_definition = [{
          alert_id    = null
          precision   = null
          text_align  = null
          title       = null
          title_align = null
          title_size  = null
          unit        = null
        }]
        change_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          live_span = null
          request = [{
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            change_type   = null
            compare_to    = null
            increase_good = null
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            order_by  = null
            order_dir = null
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            show_present = null
          }]
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        check_status_definition = [{
          check       = null
          group       = null
          group_by    = []
          grouping    = null
          live_span   = null
          tags        = []
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        distribution_definition = [{
          legend_size = null
          live_span   = null
          request = [{
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            style = [{
              palette = null
            }]
          }]
          show_legend = null
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        event_stream_definition = [{
          event_size     = null
          live_span      = null
          query          = null
          tags_execution = null
          time           = {}
          title          = null
          title_align    = null
          title_size     = null
        }]
        event_timeline_definition = [{
          live_span      = null
          query          = null
          tags_execution = null
          time           = {}
          title          = null
          title_align    = null
          title_size     = null
        }]
        free_text_definition = [{
          color      = null
          font_size  = null
          text       = null
          text_align = null
        }]
        geomap_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          live_span = null
          request = [{
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
          }]
          style = [{
            palette      = null
            palette_flip = null
          }]
          title       = null
          title_align = null
          title_size  = null
          view = [{
            focus = null
          }]
        }]
        heatmap_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          event = [{
            q              = null
            tags_execution = null
          }]
          legend_size = null
          live_span   = null
          request = [{
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            style = [{
              palette = null
            }]
          }]
          show_legend = null
          time        = {}
          title       = null
          title_align = null
          title_size  = null
          yaxis = [{
            include_zero = null
            label        = null
            max          = null
            min          = null
            scale        = null
          }]
        }]
        hostmap_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          group           = []
          no_group_hosts  = null
          no_metric_hosts = null
          node_type       = null
          request = [{
            fill = [{
              apm_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              log_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              process_query = [{
                filter_by = []
                limit     = null
                metric    = null
                search_by = null
              }]
              q = null
              rum_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              security_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
            }]
            size = [{
              apm_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              log_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              process_query = [{
                filter_by = []
                limit     = null
                metric    = null
                search_by = null
              }]
              q = null
              rum_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              security_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
            }]
          }]
          scope = []
          style = [{
            fill_max     = null
            fill_min     = null
            palette      = null
            palette_flip = null
          }]
          title       = null
          title_align = null
          title_size  = null
        }]
        id = null
        iframe_definition = [{
          url = null
        }]
        image_definition = [{
          margin = null
          sizing = null
          url    = null
        }]
        layout = {}
        log_stream_definition = [{
          columns             = []
          indexes             = []
          live_span           = null
          logset              = null
          message_display     = null
          query               = null
          show_date_column    = null
          show_message_column = null
          sort = [{
            column = null
            order  = null
          }]
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        manage_status_definition = [{
          color_preference    = null
          count               = null
          display_format      = null
          hide_zero_counts    = null
          query               = null
          show_last_triggered = null
          sort                = null
          start               = null
          summary_type        = null
          title               = null
          title_align         = null
          title_size          = null
        }]
        note_definition = [{
          background_color = null
          content          = null
          font_size        = null
          show_tick        = null
          text_align       = null
          tick_edge        = null
          tick_pos         = null
        }]
        query_table_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          has_search_bar = null
          live_span      = null
          request = [{
            aggregator = null
            alias      = null
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            apm_stats_query = [{
              columns = [{
                alias             = null
                cell_display_mode = null
                name              = null
                order             = null
              }]
              env         = null
              name        = null
              primary_tag = null
              resource    = null
              row_type    = null
              service     = null
            }]
            cell_display_mode = []
            conditional_formats = [{
              comparator      = null
              custom_bg_color = null
              custom_fg_color = null
              hide_value      = null
              image_url       = null
              metric          = null
              palette         = null
              timeframe       = null
              value           = null
            }]
            limit = null
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            order = null
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
          }]
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        query_value_definition = [{
          autoscale = null
          custom_link = [{
            label = null
            link  = null
          }]
          custom_unit = null
          live_span   = null
          precision   = null
          request = [{
            aggregator = null
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            conditional_formats = [{
              comparator      = null
              custom_bg_color = null
              custom_fg_color = null
              hide_value      = null
              image_url       = null
              metric          = null
              palette         = null
              timeframe       = null
              value           = null
            }]
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
          }]
          text_align  = null
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        scatterplot_definition = [{
          color_by_groups = []
          custom_link = [{
            label = null
            link  = null
          }]
          live_span = null
          request = [{
            x = [{
              aggregator = null
              apm_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              log_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              process_query = [{
                filter_by = []
                limit     = null
                metric    = null
                search_by = null
              }]
              q = null
              rum_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              security_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
            }]
            y = [{
              aggregator = null
              apm_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              log_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              process_query = [{
                filter_by = []
                limit     = null
                metric    = null
                search_by = null
              }]
              q = null
              rum_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
              security_query = [{
                compute = {}
                compute_query = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                group_by = [{
                  facet = null
                  limit = null
                  sort  = {}
                  sort_query = [{
                    aggregation = null
                    facet       = null
                    order       = null
                  }]
                }]
                index = null
                multi_compute = [{
                  aggregation = null
                  facet       = null
                  interval    = null
                }]
                search       = {}
                search_query = null
              }]
            }]
          }]
          time        = {}
          title       = null
          title_align = null
          title_size  = null
          xaxis = [{
            include_zero = null
            label        = null
            max          = null
            min          = null
            scale        = null
          }]
          yaxis = [{
            include_zero = null
            label        = null
            max          = null
            min          = null
            scale        = null
          }]
        }]
        service_level_objective_definition = [{
          show_error_budget = null
          slo_id            = null
          time_windows      = []
          title             = null
          title_align       = null
          title_size        = null
          view_mode         = null
          view_type         = null
        }]
        servicemap_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          filters     = []
          service     = null
          title       = null
          title_align = null
          title_size  = null
        }]
        timeseries_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          event = [{
            q              = null
            tags_execution = null
          }]
          legend_columns = []
          legend_layout  = null
          legend_size    = null
          live_span      = null
          marker = [{
            display_type = null
            label        = null
            value        = null
          }]
          request = [{
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            display_type = null
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            metadata = [{
              alias_name = null
              expression = null
            }]
            network_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            on_right_yaxis = null
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            style = [{
              line_type  = null
              line_width = null
              palette    = null
            }]
          }]
          right_yaxis = [{
            include_zero = null
            label        = null
            max          = null
            min          = null
            scale        = null
          }]
          show_legend = null
          time        = {}
          title       = null
          title_align = null
          title_size  = null
          yaxis = [{
            include_zero = null
            label        = null
            max          = null
            min          = null
            scale        = null
          }]
        }]
        toplist_definition = [{
          custom_link = [{
            label = null
            link  = null
          }]
          live_span = null
          request = [{
            apm_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            conditional_formats = [{
              comparator      = null
              custom_bg_color = null
              custom_fg_color = null
              hide_value      = null
              image_url       = null
              metric          = null
              palette         = null
              timeframe       = null
              value           = null
            }]
            log_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            process_query = [{
              filter_by = []
              limit     = null
              metric    = null
              search_by = null
            }]
            q = null
            rum_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            security_query = [{
              compute = {}
              compute_query = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              group_by = [{
                facet = null
                limit = null
                sort  = {}
                sort_query = [{
                  aggregation = null
                  facet       = null
                  order       = null
                }]
              }]
              index = null
              multi_compute = [{
                aggregation = null
                facet       = null
                interval    = null
              }]
              search       = {}
              search_query = null
            }]
            style = [{
              palette = null
            }]
          }]
          time        = {}
          title       = null
          title_align = null
          title_size  = null
        }]
        trace_service_definition = [{
          display_format     = null
          env                = null
          live_span          = null
          service            = null
          show_breakdown     = null
          show_distribution  = null
          show_errors        = null
          show_hits          = null
          show_latency       = null
          show_resource_list = null
          size_format        = null
          span_name          = null
          time               = {}
          title              = null
          title_align        = null
          title_size         = null
        }]
        widget_layout = [{
          height = null
          width  = null
          x      = null
          y      = null
        }]
      }]
    }]
    heatmap_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      event = [{
        q              = null
        tags_execution = null
      }]
      legend_size = null
      live_span   = null
      request = [{
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        style = [{
          palette = null
        }]
      }]
      show_legend = null
      time        = {}
      title       = null
      title_align = null
      title_size  = null
      yaxis = [{
        include_zero = null
        label        = null
        max          = null
        min          = null
        scale        = null
      }]
    }]
    hostmap_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      group           = []
      no_group_hosts  = null
      no_metric_hosts = null
      node_type       = null
      request = [{
        fill = [{
          apm_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          log_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          process_query = [{
            filter_by = []
            limit     = null
            metric    = null
            search_by = null
          }]
          q = null
          rum_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          security_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
        }]
        size = [{
          apm_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          log_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          process_query = [{
            filter_by = []
            limit     = null
            metric    = null
            search_by = null
          }]
          q = null
          rum_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          security_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
        }]
      }]
      scope = []
      style = [{
        fill_max     = null
        fill_min     = null
        palette      = null
        palette_flip = null
      }]
      title       = null
      title_align = null
      title_size  = null
    }]
    id = null
    iframe_definition = [{
      url = null
    }]
    image_definition = [{
      margin = null
      sizing = null
      url    = null
    }]
    layout = {}
    log_stream_definition = [{
      columns             = []
      indexes             = []
      live_span           = null
      logset              = null
      message_display     = null
      query               = null
      show_date_column    = null
      show_message_column = null
      sort = [{
        column = null
        order  = null
      }]
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    manage_status_definition = [{
      color_preference    = null
      count               = null
      display_format      = null
      hide_zero_counts    = null
      query               = null
      show_last_triggered = null
      sort                = null
      start               = null
      summary_type        = null
      title               = null
      title_align         = null
      title_size          = null
    }]
    note_definition = [{
      background_color = null
      content          = null
      font_size        = null
      show_tick        = null
      text_align       = null
      tick_edge        = null
      tick_pos         = null
    }]
    query_table_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      has_search_bar = null
      live_span      = null
      request = [{
        aggregator = null
        alias      = null
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        apm_stats_query = [{
          columns = [{
            alias             = null
            cell_display_mode = null
            name              = null
            order             = null
          }]
          env         = null
          name        = null
          primary_tag = null
          resource    = null
          row_type    = null
          service     = null
        }]
        cell_display_mode = []
        conditional_formats = [{
          comparator      = null
          custom_bg_color = null
          custom_fg_color = null
          hide_value      = null
          image_url       = null
          metric          = null
          palette         = null
          timeframe       = null
          value           = null
        }]
        limit = null
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        order = null
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
      }]
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    query_value_definition = [{
      autoscale = null
      custom_link = [{
        label = null
        link  = null
      }]
      custom_unit = null
      live_span   = null
      precision   = null
      request = [{
        aggregator = null
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        conditional_formats = [{
          comparator      = null
          custom_bg_color = null
          custom_fg_color = null
          hide_value      = null
          image_url       = null
          metric          = null
          palette         = null
          timeframe       = null
          value           = null
        }]
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
      }]
      text_align  = null
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    scatterplot_definition = [{
      color_by_groups = []
      custom_link = [{
        label = null
        link  = null
      }]
      live_span = null
      request = [{
        x = [{
          aggregator = null
          apm_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          log_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          process_query = [{
            filter_by = []
            limit     = null
            metric    = null
            search_by = null
          }]
          q = null
          rum_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          security_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
        }]
        y = [{
          aggregator = null
          apm_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          log_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          process_query = [{
            filter_by = []
            limit     = null
            metric    = null
            search_by = null
          }]
          q = null
          rum_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
          security_query = [{
            compute = {}
            compute_query = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            group_by = [{
              facet = null
              limit = null
              sort  = {}
              sort_query = [{
                aggregation = null
                facet       = null
                order       = null
              }]
            }]
            index = null
            multi_compute = [{
              aggregation = null
              facet       = null
              interval    = null
            }]
            search       = {}
            search_query = null
          }]
        }]
      }]
      time        = {}
      title       = null
      title_align = null
      title_size  = null
      xaxis = [{
        include_zero = null
        label        = null
        max          = null
        min          = null
        scale        = null
      }]
      yaxis = [{
        include_zero = null
        label        = null
        max          = null
        min          = null
        scale        = null
      }]
    }]
    service_level_objective_definition = [{
      show_error_budget = null
      slo_id            = null
      time_windows      = []
      title             = null
      title_align       = null
      title_size        = null
      view_mode         = null
      view_type         = null
    }]
    servicemap_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      filters     = []
      service     = null
      title       = null
      title_align = null
      title_size  = null
    }]
    timeseries_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      event = [{
        q              = null
        tags_execution = null
      }]
      legend_columns = []
      legend_layout  = null
      legend_size    = null
      live_span      = null
      marker = [{
        display_type = null
        label        = null
        value        = null
      }]
      request = [{
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        display_type = null
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        metadata = [{
          alias_name = null
          expression = null
        }]
        network_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        on_right_yaxis = null
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        style = [{
          line_type  = null
          line_width = null
          palette    = null
        }]
      }]
      right_yaxis = [{
        include_zero = null
        label        = null
        max          = null
        min          = null
        scale        = null
      }]
      show_legend = null
      time        = {}
      title       = null
      title_align = null
      title_size  = null
      yaxis = [{
        include_zero = null
        label        = null
        max          = null
        min          = null
        scale        = null
      }]
    }]
    toplist_definition = [{
      custom_link = [{
        label = null
        link  = null
      }]
      live_span = null
      request = [{
        apm_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        conditional_formats = [{
          comparator      = null
          custom_bg_color = null
          custom_fg_color = null
          hide_value      = null
          image_url       = null
          metric          = null
          palette         = null
          timeframe       = null
          value           = null
        }]
        log_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        process_query = [{
          filter_by = []
          limit     = null
          metric    = null
          search_by = null
        }]
        q = null
        rum_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        security_query = [{
          compute = {}
          compute_query = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          group_by = [{
            facet = null
            limit = null
            sort  = {}
            sort_query = [{
              aggregation = null
              facet       = null
              order       = null
            }]
          }]
          index = null
          multi_compute = [{
            aggregation = null
            facet       = null
            interval    = null
          }]
          search       = {}
          search_query = null
        }]
        style = [{
          palette = null
        }]
      }]
      time        = {}
      title       = null
      title_align = null
      title_size  = null
    }]
    trace_service_definition = [{
      display_format     = null
      env                = null
      live_span          = null
      service            = null
      show_breakdown     = null
      show_distribution  = null
      show_errors        = null
      show_hits          = null
      show_latency       = null
      show_resource_list = null
      size_format        = null
      span_name          = null
      time               = {}
      title              = null
      title_align        = null
      title_size         = null
    }]
    widget_layout = [{
      height = null
      width  = null
      x      = null
      y      = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dashboard_lists" {
  description = "(optional) - The list of dashboard lists this dashboard belongs to."
  type        = set(number)
  default     = null
}

variable "description" {
  description = "(optional) - The description of the dashboard."
  type        = string
  default     = null
}

variable "is_read_only" {
  description = "(optional) - Whether this dashboard is read-only."
  type        = bool
  default     = null
}

variable "layout_type" {
  description = "(required) - The layout type of the dashboard, either 'free' or 'ordered'."
  type        = string
}

variable "notify_list" {
  description = "(optional) - The list of handles of users to notify when changes are made to this dashboard."
  type        = list(string)
  default     = null
}

variable "title" {
  description = "(required) - The title of the dashboard."
  type        = string
}

variable "url" {
  description = "(optional) - The URL of the dashboard."
  type        = string
  default     = null
}

variable "template_variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
      name    = string
      prefix  = string
    }
  ))
  default = []
}

variable "template_variable_preset" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      template_variable = list(object(
        {
          name  = string
          value = string
        }
      ))
    }
  ))
  default = []
}

variable "widget" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      alert_graph_definition = list(object(
        {
          alert_id    = string
          live_span   = string
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
          viz_type    = string
        }
      ))
      alert_value_definition = list(object(
        {
          alert_id    = string
          precision   = number
          text_align  = string
          title       = string
          title_align = string
          title_size  = string
          unit        = string
        }
      ))
      change_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          live_span = string
          request = list(object(
            {
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              change_type   = string
              compare_to    = string
              increase_good = bool
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              order_by  = string
              order_dir = string
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              show_present = bool
            }
          ))
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      check_status_definition = list(object(
        {
          check       = string
          group       = string
          group_by    = list(string)
          grouping    = string
          live_span   = string
          tags        = list(string)
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      distribution_definition = list(object(
        {
          legend_size = string
          live_span   = string
          request = list(object(
            {
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              style = list(object(
                {
                  palette = string
                }
              ))
            }
          ))
          show_legend = bool
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      event_stream_definition = list(object(
        {
          event_size     = string
          live_span      = string
          query          = string
          tags_execution = string
          time           = map(string)
          title          = string
          title_align    = string
          title_size     = string
        }
      ))
      event_timeline_definition = list(object(
        {
          live_span      = string
          query          = string
          tags_execution = string
          time           = map(string)
          title          = string
          title_align    = string
          title_size     = string
        }
      ))
      free_text_definition = list(object(
        {
          color      = string
          font_size  = string
          text       = string
          text_align = string
        }
      ))
      geomap_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          live_span = string
          request = list(object(
            {
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
            }
          ))
          style = list(object(
            {
              palette      = string
              palette_flip = bool
            }
          ))
          title       = string
          title_align = string
          title_size  = string
          view = list(object(
            {
              focus = string
            }
          ))
        }
      ))
      group_definition = list(object(
        {
          layout_type = string
          title       = string
          widget = list(object(
            {
              alert_graph_definition = list(object(
                {
                  alert_id    = string
                  live_span   = string
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                  viz_type    = string
                }
              ))
              alert_value_definition = list(object(
                {
                  alert_id    = string
                  precision   = number
                  text_align  = string
                  title       = string
                  title_align = string
                  title_size  = string
                  unit        = string
                }
              ))
              change_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  live_span = string
                  request = list(object(
                    {
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      change_type   = string
                      compare_to    = string
                      increase_good = bool
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      order_by  = string
                      order_dir = string
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      show_present = bool
                    }
                  ))
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              check_status_definition = list(object(
                {
                  check       = string
                  group       = string
                  group_by    = list(string)
                  grouping    = string
                  live_span   = string
                  tags        = list(string)
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              distribution_definition = list(object(
                {
                  legend_size = string
                  live_span   = string
                  request = list(object(
                    {
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      style = list(object(
                        {
                          palette = string
                        }
                      ))
                    }
                  ))
                  show_legend = bool
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              event_stream_definition = list(object(
                {
                  event_size     = string
                  live_span      = string
                  query          = string
                  tags_execution = string
                  time           = map(string)
                  title          = string
                  title_align    = string
                  title_size     = string
                }
              ))
              event_timeline_definition = list(object(
                {
                  live_span      = string
                  query          = string
                  tags_execution = string
                  time           = map(string)
                  title          = string
                  title_align    = string
                  title_size     = string
                }
              ))
              free_text_definition = list(object(
                {
                  color      = string
                  font_size  = string
                  text       = string
                  text_align = string
                }
              ))
              geomap_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  live_span = string
                  request = list(object(
                    {
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                    }
                  ))
                  style = list(object(
                    {
                      palette      = string
                      palette_flip = bool
                    }
                  ))
                  title       = string
                  title_align = string
                  title_size  = string
                  view = list(object(
                    {
                      focus = string
                    }
                  ))
                }
              ))
              heatmap_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  event = list(object(
                    {
                      q              = string
                      tags_execution = string
                    }
                  ))
                  legend_size = string
                  live_span   = string
                  request = list(object(
                    {
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      style = list(object(
                        {
                          palette = string
                        }
                      ))
                    }
                  ))
                  show_legend = bool
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                  yaxis = list(object(
                    {
                      include_zero = bool
                      label        = string
                      max          = string
                      min          = string
                      scale        = string
                    }
                  ))
                }
              ))
              hostmap_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  group           = list(string)
                  no_group_hosts  = bool
                  no_metric_hosts = bool
                  node_type       = string
                  request = list(object(
                    {
                      fill = list(object(
                        {
                          apm_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          log_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          process_query = list(object(
                            {
                              filter_by = list(string)
                              limit     = number
                              metric    = string
                              search_by = string
                            }
                          ))
                          q = string
                          rum_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          security_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                        }
                      ))
                      size = list(object(
                        {
                          apm_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          log_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          process_query = list(object(
                            {
                              filter_by = list(string)
                              limit     = number
                              metric    = string
                              search_by = string
                            }
                          ))
                          q = string
                          rum_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          security_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  scope = list(string)
                  style = list(object(
                    {
                      fill_max     = string
                      fill_min     = string
                      palette      = string
                      palette_flip = bool
                    }
                  ))
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              id = number
              iframe_definition = list(object(
                {
                  url = string
                }
              ))
              image_definition = list(object(
                {
                  margin = string
                  sizing = string
                  url    = string
                }
              ))
              layout = map(string)
              log_stream_definition = list(object(
                {
                  columns             = list(string)
                  indexes             = list(string)
                  live_span           = string
                  logset              = string
                  message_display     = string
                  query               = string
                  show_date_column    = bool
                  show_message_column = bool
                  sort = list(object(
                    {
                      column = string
                      order  = string
                    }
                  ))
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              manage_status_definition = list(object(
                {
                  color_preference    = string
                  count               = number
                  display_format      = string
                  hide_zero_counts    = bool
                  query               = string
                  show_last_triggered = bool
                  sort                = string
                  start               = number
                  summary_type        = string
                  title               = string
                  title_align         = string
                  title_size          = string
                }
              ))
              note_definition = list(object(
                {
                  background_color = string
                  content          = string
                  font_size        = string
                  show_tick        = bool
                  text_align       = string
                  tick_edge        = string
                  tick_pos         = string
                }
              ))
              query_table_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  has_search_bar = string
                  live_span      = string
                  request = list(object(
                    {
                      aggregator = string
                      alias      = string
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      apm_stats_query = list(object(
                        {
                          columns = list(object(
                            {
                              alias             = string
                              cell_display_mode = string
                              name              = string
                              order             = string
                            }
                          ))
                          env         = string
                          name        = string
                          primary_tag = string
                          resource    = string
                          row_type    = string
                          service     = string
                        }
                      ))
                      cell_display_mode = list(string)
                      conditional_formats = list(object(
                        {
                          comparator      = string
                          custom_bg_color = string
                          custom_fg_color = string
                          hide_value      = bool
                          image_url       = string
                          metric          = string
                          palette         = string
                          timeframe       = string
                          value           = number
                        }
                      ))
                      limit = number
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      order = string
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                    }
                  ))
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              query_value_definition = list(object(
                {
                  autoscale = bool
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  custom_unit = string
                  live_span   = string
                  precision   = number
                  request = list(object(
                    {
                      aggregator = string
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      conditional_formats = list(object(
                        {
                          comparator      = string
                          custom_bg_color = string
                          custom_fg_color = string
                          hide_value      = bool
                          image_url       = string
                          metric          = string
                          palette         = string
                          timeframe       = string
                          value           = number
                        }
                      ))
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                    }
                  ))
                  text_align  = string
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              scatterplot_definition = list(object(
                {
                  color_by_groups = list(string)
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  live_span = string
                  request = list(object(
                    {
                      x = list(object(
                        {
                          aggregator = string
                          apm_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          log_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          process_query = list(object(
                            {
                              filter_by = list(string)
                              limit     = number
                              metric    = string
                              search_by = string
                            }
                          ))
                          q = string
                          rum_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          security_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                        }
                      ))
                      y = list(object(
                        {
                          aggregator = string
                          apm_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          log_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          process_query = list(object(
                            {
                              filter_by = list(string)
                              limit     = number
                              metric    = string
                              search_by = string
                            }
                          ))
                          q = string
                          rum_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                          security_query = list(object(
                            {
                              compute = map(string)
                              compute_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              group_by = list(object(
                                {
                                  facet = string
                                  limit = number
                                  sort  = map(string)
                                  sort_query = list(object(
                                    {
                                      aggregation = string
                                      facet       = string
                                      order       = string
                                    }
                                  ))
                                }
                              ))
                              index = string
                              multi_compute = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  interval    = number
                                }
                              ))
                              search       = map(string)
                              search_query = string
                            }
                          ))
                        }
                      ))
                    }
                  ))
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                  xaxis = list(object(
                    {
                      include_zero = bool
                      label        = string
                      max          = string
                      min          = string
                      scale        = string
                    }
                  ))
                  yaxis = list(object(
                    {
                      include_zero = bool
                      label        = string
                      max          = string
                      min          = string
                      scale        = string
                    }
                  ))
                }
              ))
              service_level_objective_definition = list(object(
                {
                  show_error_budget = bool
                  slo_id            = string
                  time_windows      = list(string)
                  title             = string
                  title_align       = string
                  title_size        = string
                  view_mode         = string
                  view_type         = string
                }
              ))
              servicemap_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  filters     = list(string)
                  service     = string
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              timeseries_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  event = list(object(
                    {
                      q              = string
                      tags_execution = string
                    }
                  ))
                  legend_columns = set(string)
                  legend_layout  = string
                  legend_size    = string
                  live_span      = string
                  marker = list(object(
                    {
                      display_type = string
                      label        = string
                      value        = string
                    }
                  ))
                  request = list(object(
                    {
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      display_type = string
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      metadata = list(object(
                        {
                          alias_name = string
                          expression = string
                        }
                      ))
                      network_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      on_right_yaxis = bool
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      style = list(object(
                        {
                          line_type  = string
                          line_width = string
                          palette    = string
                        }
                      ))
                    }
                  ))
                  right_yaxis = list(object(
                    {
                      include_zero = bool
                      label        = string
                      max          = string
                      min          = string
                      scale        = string
                    }
                  ))
                  show_legend = bool
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                  yaxis = list(object(
                    {
                      include_zero = bool
                      label        = string
                      max          = string
                      min          = string
                      scale        = string
                    }
                  ))
                }
              ))
              toplist_definition = list(object(
                {
                  custom_link = list(object(
                    {
                      label = string
                      link  = string
                    }
                  ))
                  live_span = string
                  request = list(object(
                    {
                      apm_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      conditional_formats = list(object(
                        {
                          comparator      = string
                          custom_bg_color = string
                          custom_fg_color = string
                          hide_value      = bool
                          image_url       = string
                          metric          = string
                          palette         = string
                          timeframe       = string
                          value           = number
                        }
                      ))
                      log_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      process_query = list(object(
                        {
                          filter_by = list(string)
                          limit     = number
                          metric    = string
                          search_by = string
                        }
                      ))
                      q = string
                      rum_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      security_query = list(object(
                        {
                          compute = map(string)
                          compute_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          group_by = list(object(
                            {
                              facet = string
                              limit = number
                              sort  = map(string)
                              sort_query = list(object(
                                {
                                  aggregation = string
                                  facet       = string
                                  order       = string
                                }
                              ))
                            }
                          ))
                          index = string
                          multi_compute = list(object(
                            {
                              aggregation = string
                              facet       = string
                              interval    = number
                            }
                          ))
                          search       = map(string)
                          search_query = string
                        }
                      ))
                      style = list(object(
                        {
                          palette = string
                        }
                      ))
                    }
                  ))
                  time        = map(string)
                  title       = string
                  title_align = string
                  title_size  = string
                }
              ))
              trace_service_definition = list(object(
                {
                  display_format     = string
                  env                = string
                  live_span          = string
                  service            = string
                  show_breakdown     = bool
                  show_distribution  = bool
                  show_errors        = bool
                  show_hits          = bool
                  show_latency       = bool
                  show_resource_list = bool
                  size_format        = string
                  span_name          = string
                  time               = map(string)
                  title              = string
                  title_align        = string
                  title_size         = string
                }
              ))
              widget_layout = list(object(
                {
                  height = number
                  width  = number
                  x      = number
                  y      = number
                }
              ))
            }
          ))
        }
      ))
      heatmap_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          event = list(object(
            {
              q              = string
              tags_execution = string
            }
          ))
          legend_size = string
          live_span   = string
          request = list(object(
            {
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              style = list(object(
                {
                  palette = string
                }
              ))
            }
          ))
          show_legend = bool
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
          yaxis = list(object(
            {
              include_zero = bool
              label        = string
              max          = string
              min          = string
              scale        = string
            }
          ))
        }
      ))
      hostmap_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          group           = list(string)
          no_group_hosts  = bool
          no_metric_hosts = bool
          node_type       = string
          request = list(object(
            {
              fill = list(object(
                {
                  apm_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  log_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  process_query = list(object(
                    {
                      filter_by = list(string)
                      limit     = number
                      metric    = string
                      search_by = string
                    }
                  ))
                  q = string
                  rum_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  security_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                }
              ))
              size = list(object(
                {
                  apm_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  log_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  process_query = list(object(
                    {
                      filter_by = list(string)
                      limit     = number
                      metric    = string
                      search_by = string
                    }
                  ))
                  q = string
                  rum_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  security_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                }
              ))
            }
          ))
          scope = list(string)
          style = list(object(
            {
              fill_max     = string
              fill_min     = string
              palette      = string
              palette_flip = bool
            }
          ))
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      id = number
      iframe_definition = list(object(
        {
          url = string
        }
      ))
      image_definition = list(object(
        {
          margin = string
          sizing = string
          url    = string
        }
      ))
      layout = map(string)
      log_stream_definition = list(object(
        {
          columns             = list(string)
          indexes             = list(string)
          live_span           = string
          logset              = string
          message_display     = string
          query               = string
          show_date_column    = bool
          show_message_column = bool
          sort = list(object(
            {
              column = string
              order  = string
            }
          ))
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      manage_status_definition = list(object(
        {
          color_preference    = string
          count               = number
          display_format      = string
          hide_zero_counts    = bool
          query               = string
          show_last_triggered = bool
          sort                = string
          start               = number
          summary_type        = string
          title               = string
          title_align         = string
          title_size          = string
        }
      ))
      note_definition = list(object(
        {
          background_color = string
          content          = string
          font_size        = string
          show_tick        = bool
          text_align       = string
          tick_edge        = string
          tick_pos         = string
        }
      ))
      query_table_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          has_search_bar = string
          live_span      = string
          request = list(object(
            {
              aggregator = string
              alias      = string
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              apm_stats_query = list(object(
                {
                  columns = list(object(
                    {
                      alias             = string
                      cell_display_mode = string
                      name              = string
                      order             = string
                    }
                  ))
                  env         = string
                  name        = string
                  primary_tag = string
                  resource    = string
                  row_type    = string
                  service     = string
                }
              ))
              cell_display_mode = list(string)
              conditional_formats = list(object(
                {
                  comparator      = string
                  custom_bg_color = string
                  custom_fg_color = string
                  hide_value      = bool
                  image_url       = string
                  metric          = string
                  palette         = string
                  timeframe       = string
                  value           = number
                }
              ))
              limit = number
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              order = string
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
            }
          ))
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      query_value_definition = list(object(
        {
          autoscale = bool
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          custom_unit = string
          live_span   = string
          precision   = number
          request = list(object(
            {
              aggregator = string
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              conditional_formats = list(object(
                {
                  comparator      = string
                  custom_bg_color = string
                  custom_fg_color = string
                  hide_value      = bool
                  image_url       = string
                  metric          = string
                  palette         = string
                  timeframe       = string
                  value           = number
                }
              ))
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
            }
          ))
          text_align  = string
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      scatterplot_definition = list(object(
        {
          color_by_groups = list(string)
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          live_span = string
          request = list(object(
            {
              x = list(object(
                {
                  aggregator = string
                  apm_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  log_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  process_query = list(object(
                    {
                      filter_by = list(string)
                      limit     = number
                      metric    = string
                      search_by = string
                    }
                  ))
                  q = string
                  rum_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  security_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                }
              ))
              y = list(object(
                {
                  aggregator = string
                  apm_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  log_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  process_query = list(object(
                    {
                      filter_by = list(string)
                      limit     = number
                      metric    = string
                      search_by = string
                    }
                  ))
                  q = string
                  rum_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                  security_query = list(object(
                    {
                      compute = map(string)
                      compute_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      group_by = list(object(
                        {
                          facet = string
                          limit = number
                          sort  = map(string)
                          sort_query = list(object(
                            {
                              aggregation = string
                              facet       = string
                              order       = string
                            }
                          ))
                        }
                      ))
                      index = string
                      multi_compute = list(object(
                        {
                          aggregation = string
                          facet       = string
                          interval    = number
                        }
                      ))
                      search       = map(string)
                      search_query = string
                    }
                  ))
                }
              ))
            }
          ))
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
          xaxis = list(object(
            {
              include_zero = bool
              label        = string
              max          = string
              min          = string
              scale        = string
            }
          ))
          yaxis = list(object(
            {
              include_zero = bool
              label        = string
              max          = string
              min          = string
              scale        = string
            }
          ))
        }
      ))
      service_level_objective_definition = list(object(
        {
          show_error_budget = bool
          slo_id            = string
          time_windows      = list(string)
          title             = string
          title_align       = string
          title_size        = string
          view_mode         = string
          view_type         = string
        }
      ))
      servicemap_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          filters     = list(string)
          service     = string
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      timeseries_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          event = list(object(
            {
              q              = string
              tags_execution = string
            }
          ))
          legend_columns = set(string)
          legend_layout  = string
          legend_size    = string
          live_span      = string
          marker = list(object(
            {
              display_type = string
              label        = string
              value        = string
            }
          ))
          request = list(object(
            {
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              display_type = string
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              metadata = list(object(
                {
                  alias_name = string
                  expression = string
                }
              ))
              network_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              on_right_yaxis = bool
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              style = list(object(
                {
                  line_type  = string
                  line_width = string
                  palette    = string
                }
              ))
            }
          ))
          right_yaxis = list(object(
            {
              include_zero = bool
              label        = string
              max          = string
              min          = string
              scale        = string
            }
          ))
          show_legend = bool
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
          yaxis = list(object(
            {
              include_zero = bool
              label        = string
              max          = string
              min          = string
              scale        = string
            }
          ))
        }
      ))
      toplist_definition = list(object(
        {
          custom_link = list(object(
            {
              label = string
              link  = string
            }
          ))
          live_span = string
          request = list(object(
            {
              apm_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              conditional_formats = list(object(
                {
                  comparator      = string
                  custom_bg_color = string
                  custom_fg_color = string
                  hide_value      = bool
                  image_url       = string
                  metric          = string
                  palette         = string
                  timeframe       = string
                  value           = number
                }
              ))
              log_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              process_query = list(object(
                {
                  filter_by = list(string)
                  limit     = number
                  metric    = string
                  search_by = string
                }
              ))
              q = string
              rum_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              security_query = list(object(
                {
                  compute = map(string)
                  compute_query = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  group_by = list(object(
                    {
                      facet = string
                      limit = number
                      sort  = map(string)
                      sort_query = list(object(
                        {
                          aggregation = string
                          facet       = string
                          order       = string
                        }
                      ))
                    }
                  ))
                  index = string
                  multi_compute = list(object(
                    {
                      aggregation = string
                      facet       = string
                      interval    = number
                    }
                  ))
                  search       = map(string)
                  search_query = string
                }
              ))
              style = list(object(
                {
                  palette = string
                }
              ))
            }
          ))
          time        = map(string)
          title       = string
          title_align = string
          title_size  = string
        }
      ))
      trace_service_definition = list(object(
        {
          display_format     = string
          env                = string
          live_span          = string
          service            = string
          show_breakdown     = bool
          show_distribution  = bool
          show_errors        = bool
          show_hits          = bool
          show_latency       = bool
          show_resource_list = bool
          size_format        = string
          span_name          = string
          time               = map(string)
          title              = string
          title_align        = string
          title_size         = string
        }
      ))
      widget_layout = list(object(
        {
          height = number
          width  = number
          x      = number
          y      = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "datadog_dashboard" "this" {
  # dashboard_lists - (optional) is a type of set of number
  dashboard_lists = var.dashboard_lists
  # description - (optional) is a type of string
  description = var.description
  # is_read_only - (optional) is a type of bool
  is_read_only = var.is_read_only
  # layout_type - (required) is a type of string
  layout_type = var.layout_type
  # notify_list - (optional) is a type of list of string
  notify_list = var.notify_list
  # title - (required) is a type of string
  title = var.title
  # url - (optional) is a type of string
  url = var.url

  dynamic "template_variable" {
    for_each = var.template_variable
    content {
      # default - (optional) is a type of string
      default = template_variable.value["default"]
      # name - (required) is a type of string
      name = template_variable.value["name"]
      # prefix - (optional) is a type of string
      prefix = template_variable.value["prefix"]
    }
  }

  dynamic "template_variable_preset" {
    for_each = var.template_variable_preset
    content {
      # name - (optional) is a type of string
      name = template_variable_preset.value["name"]

      dynamic "template_variable" {
        for_each = template_variable_preset.value.template_variable
        content {
          # name - (optional) is a type of string
          name = template_variable.value["name"]
          # value - (optional) is a type of string
          value = template_variable.value["value"]
        }
      }

    }
  }

  dynamic "widget" {
    for_each = var.widget
    content {
      # layout - (optional) is a type of map of string
      layout = widget.value["layout"]

      dynamic "alert_graph_definition" {
        for_each = widget.value.alert_graph_definition
        content {
          # alert_id - (required) is a type of string
          alert_id = alert_graph_definition.value["alert_id"]
          # live_span - (optional) is a type of string
          live_span = alert_graph_definition.value["live_span"]
          # time - (optional) is a type of map of string
          time = alert_graph_definition.value["time"]
          # title - (optional) is a type of string
          title = alert_graph_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = alert_graph_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = alert_graph_definition.value["title_size"]
          # viz_type - (required) is a type of string
          viz_type = alert_graph_definition.value["viz_type"]
        }
      }

      dynamic "alert_value_definition" {
        for_each = widget.value.alert_value_definition
        content {
          # alert_id - (required) is a type of string
          alert_id = alert_value_definition.value["alert_id"]
          # precision - (optional) is a type of number
          precision = alert_value_definition.value["precision"]
          # text_align - (optional) is a type of string
          text_align = alert_value_definition.value["text_align"]
          # title - (optional) is a type of string
          title = alert_value_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = alert_value_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = alert_value_definition.value["title_size"]
          # unit - (optional) is a type of string
          unit = alert_value_definition.value["unit"]
        }
      }

      dynamic "change_definition" {
        for_each = widget.value.change_definition
        content {
          # live_span - (optional) is a type of string
          live_span = change_definition.value["live_span"]
          # time - (optional) is a type of map of string
          time = change_definition.value["time"]
          # title - (optional) is a type of string
          title = change_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = change_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = change_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = change_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = change_definition.value.request
            content {
              # change_type - (optional) is a type of string
              change_type = request.value["change_type"]
              # compare_to - (optional) is a type of string
              compare_to = request.value["compare_to"]
              # increase_good - (optional) is a type of bool
              increase_good = request.value["increase_good"]
              # order_by - (optional) is a type of string
              order_by = request.value["order_by"]
              # order_dir - (optional) is a type of string
              order_dir = request.value["order_dir"]
              # q - (optional) is a type of string
              q = request.value["q"]
              # show_present - (optional) is a type of bool
              show_present = request.value["show_present"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "check_status_definition" {
        for_each = widget.value.check_status_definition
        content {
          # check - (required) is a type of string
          check = check_status_definition.value["check"]
          # group - (optional) is a type of string
          group = check_status_definition.value["group"]
          # group_by - (optional) is a type of list of string
          group_by = check_status_definition.value["group_by"]
          # grouping - (required) is a type of string
          grouping = check_status_definition.value["grouping"]
          # live_span - (optional) is a type of string
          live_span = check_status_definition.value["live_span"]
          # tags - (optional) is a type of list of string
          tags = check_status_definition.value["tags"]
          # time - (optional) is a type of map of string
          time = check_status_definition.value["time"]
          # title - (optional) is a type of string
          title = check_status_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = check_status_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = check_status_definition.value["title_size"]
        }
      }

      dynamic "distribution_definition" {
        for_each = widget.value.distribution_definition
        content {
          # legend_size - (optional) is a type of string
          legend_size = distribution_definition.value["legend_size"]
          # live_span - (optional) is a type of string
          live_span = distribution_definition.value["live_span"]
          # show_legend - (optional) is a type of bool
          show_legend = distribution_definition.value["show_legend"]
          # time - (optional) is a type of map of string
          time = distribution_definition.value["time"]
          # title - (optional) is a type of string
          title = distribution_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = distribution_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = distribution_definition.value["title_size"]

          dynamic "request" {
            for_each = distribution_definition.value.request
            content {
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "style" {
                for_each = request.value.style
                content {
                  # palette - (optional) is a type of string
                  palette = style.value["palette"]
                }
              }

            }
          }

        }
      }

      dynamic "event_stream_definition" {
        for_each = widget.value.event_stream_definition
        content {
          # event_size - (optional) is a type of string
          event_size = event_stream_definition.value["event_size"]
          # live_span - (optional) is a type of string
          live_span = event_stream_definition.value["live_span"]
          # query - (required) is a type of string
          query = event_stream_definition.value["query"]
          # tags_execution - (optional) is a type of string
          tags_execution = event_stream_definition.value["tags_execution"]
          # time - (optional) is a type of map of string
          time = event_stream_definition.value["time"]
          # title - (optional) is a type of string
          title = event_stream_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = event_stream_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = event_stream_definition.value["title_size"]
        }
      }

      dynamic "event_timeline_definition" {
        for_each = widget.value.event_timeline_definition
        content {
          # live_span - (optional) is a type of string
          live_span = event_timeline_definition.value["live_span"]
          # query - (required) is a type of string
          query = event_timeline_definition.value["query"]
          # tags_execution - (optional) is a type of string
          tags_execution = event_timeline_definition.value["tags_execution"]
          # time - (optional) is a type of map of string
          time = event_timeline_definition.value["time"]
          # title - (optional) is a type of string
          title = event_timeline_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = event_timeline_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = event_timeline_definition.value["title_size"]
        }
      }

      dynamic "free_text_definition" {
        for_each = widget.value.free_text_definition
        content {
          # color - (optional) is a type of string
          color = free_text_definition.value["color"]
          # font_size - (optional) is a type of string
          font_size = free_text_definition.value["font_size"]
          # text - (required) is a type of string
          text = free_text_definition.value["text"]
          # text_align - (optional) is a type of string
          text_align = free_text_definition.value["text_align"]
        }
      }

      dynamic "geomap_definition" {
        for_each = widget.value.geomap_definition
        content {
          # live_span - (optional) is a type of string
          live_span = geomap_definition.value["live_span"]
          # title - (optional) is a type of string
          title = geomap_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = geomap_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = geomap_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = geomap_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = geomap_definition.value.request
            content {
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

            }
          }

          dynamic "style" {
            for_each = geomap_definition.value.style
            content {
              # palette - (required) is a type of string
              palette = style.value["palette"]
              # palette_flip - (required) is a type of bool
              palette_flip = style.value["palette_flip"]
            }
          }

          dynamic "view" {
            for_each = geomap_definition.value.view
            content {
              # focus - (required) is a type of string
              focus = view.value["focus"]
            }
          }

        }
      }

      dynamic "group_definition" {
        for_each = widget.value.group_definition
        content {
          # layout_type - (required) is a type of string
          layout_type = group_definition.value["layout_type"]
          # title - (optional) is a type of string
          title = group_definition.value["title"]

          dynamic "widget" {
            for_each = group_definition.value.widget
            content {
              # layout - (optional) is a type of map of string
              layout = widget.value["layout"]

              dynamic "alert_graph_definition" {
                for_each = widget.value.alert_graph_definition
                content {
                  # alert_id - (required) is a type of string
                  alert_id = alert_graph_definition.value["alert_id"]
                  # live_span - (optional) is a type of string
                  live_span = alert_graph_definition.value["live_span"]
                  # time - (optional) is a type of map of string
                  time = alert_graph_definition.value["time"]
                  # title - (optional) is a type of string
                  title = alert_graph_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = alert_graph_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = alert_graph_definition.value["title_size"]
                  # viz_type - (required) is a type of string
                  viz_type = alert_graph_definition.value["viz_type"]
                }
              }

              dynamic "alert_value_definition" {
                for_each = widget.value.alert_value_definition
                content {
                  # alert_id - (required) is a type of string
                  alert_id = alert_value_definition.value["alert_id"]
                  # precision - (optional) is a type of number
                  precision = alert_value_definition.value["precision"]
                  # text_align - (optional) is a type of string
                  text_align = alert_value_definition.value["text_align"]
                  # title - (optional) is a type of string
                  title = alert_value_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = alert_value_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = alert_value_definition.value["title_size"]
                  # unit - (optional) is a type of string
                  unit = alert_value_definition.value["unit"]
                }
              }

              dynamic "change_definition" {
                for_each = widget.value.change_definition
                content {
                  # live_span - (optional) is a type of string
                  live_span = change_definition.value["live_span"]
                  # time - (optional) is a type of map of string
                  time = change_definition.value["time"]
                  # title - (optional) is a type of string
                  title = change_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = change_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = change_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = change_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = change_definition.value.request
                    content {
                      # change_type - (optional) is a type of string
                      change_type = request.value["change_type"]
                      # compare_to - (optional) is a type of string
                      compare_to = request.value["compare_to"]
                      # increase_good - (optional) is a type of bool
                      increase_good = request.value["increase_good"]
                      # order_by - (optional) is a type of string
                      order_by = request.value["order_by"]
                      # order_dir - (optional) is a type of string
                      order_dir = request.value["order_dir"]
                      # q - (optional) is a type of string
                      q = request.value["q"]
                      # show_present - (optional) is a type of bool
                      show_present = request.value["show_present"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "check_status_definition" {
                for_each = widget.value.check_status_definition
                content {
                  # check - (required) is a type of string
                  check = check_status_definition.value["check"]
                  # group - (optional) is a type of string
                  group = check_status_definition.value["group"]
                  # group_by - (optional) is a type of list of string
                  group_by = check_status_definition.value["group_by"]
                  # grouping - (required) is a type of string
                  grouping = check_status_definition.value["grouping"]
                  # live_span - (optional) is a type of string
                  live_span = check_status_definition.value["live_span"]
                  # tags - (optional) is a type of list of string
                  tags = check_status_definition.value["tags"]
                  # time - (optional) is a type of map of string
                  time = check_status_definition.value["time"]
                  # title - (optional) is a type of string
                  title = check_status_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = check_status_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = check_status_definition.value["title_size"]
                }
              }

              dynamic "distribution_definition" {
                for_each = widget.value.distribution_definition
                content {
                  # legend_size - (optional) is a type of string
                  legend_size = distribution_definition.value["legend_size"]
                  # live_span - (optional) is a type of string
                  live_span = distribution_definition.value["live_span"]
                  # show_legend - (optional) is a type of bool
                  show_legend = distribution_definition.value["show_legend"]
                  # time - (optional) is a type of map of string
                  time = distribution_definition.value["time"]
                  # title - (optional) is a type of string
                  title = distribution_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = distribution_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = distribution_definition.value["title_size"]

                  dynamic "request" {
                    for_each = distribution_definition.value.request
                    content {
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "style" {
                        for_each = request.value.style
                        content {
                          # palette - (optional) is a type of string
                          palette = style.value["palette"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "event_stream_definition" {
                for_each = widget.value.event_stream_definition
                content {
                  # event_size - (optional) is a type of string
                  event_size = event_stream_definition.value["event_size"]
                  # live_span - (optional) is a type of string
                  live_span = event_stream_definition.value["live_span"]
                  # query - (required) is a type of string
                  query = event_stream_definition.value["query"]
                  # tags_execution - (optional) is a type of string
                  tags_execution = event_stream_definition.value["tags_execution"]
                  # time - (optional) is a type of map of string
                  time = event_stream_definition.value["time"]
                  # title - (optional) is a type of string
                  title = event_stream_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = event_stream_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = event_stream_definition.value["title_size"]
                }
              }

              dynamic "event_timeline_definition" {
                for_each = widget.value.event_timeline_definition
                content {
                  # live_span - (optional) is a type of string
                  live_span = event_timeline_definition.value["live_span"]
                  # query - (required) is a type of string
                  query = event_timeline_definition.value["query"]
                  # tags_execution - (optional) is a type of string
                  tags_execution = event_timeline_definition.value["tags_execution"]
                  # time - (optional) is a type of map of string
                  time = event_timeline_definition.value["time"]
                  # title - (optional) is a type of string
                  title = event_timeline_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = event_timeline_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = event_timeline_definition.value["title_size"]
                }
              }

              dynamic "free_text_definition" {
                for_each = widget.value.free_text_definition
                content {
                  # color - (optional) is a type of string
                  color = free_text_definition.value["color"]
                  # font_size - (optional) is a type of string
                  font_size = free_text_definition.value["font_size"]
                  # text - (required) is a type of string
                  text = free_text_definition.value["text"]
                  # text_align - (optional) is a type of string
                  text_align = free_text_definition.value["text_align"]
                }
              }

              dynamic "geomap_definition" {
                for_each = widget.value.geomap_definition
                content {
                  # live_span - (optional) is a type of string
                  live_span = geomap_definition.value["live_span"]
                  # title - (optional) is a type of string
                  title = geomap_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = geomap_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = geomap_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = geomap_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = geomap_definition.value.request
                    content {
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "style" {
                    for_each = geomap_definition.value.style
                    content {
                      # palette - (required) is a type of string
                      palette = style.value["palette"]
                      # palette_flip - (required) is a type of bool
                      palette_flip = style.value["palette_flip"]
                    }
                  }

                  dynamic "view" {
                    for_each = geomap_definition.value.view
                    content {
                      # focus - (required) is a type of string
                      focus = view.value["focus"]
                    }
                  }

                }
              }

              dynamic "heatmap_definition" {
                for_each = widget.value.heatmap_definition
                content {
                  # legend_size - (optional) is a type of string
                  legend_size = heatmap_definition.value["legend_size"]
                  # live_span - (optional) is a type of string
                  live_span = heatmap_definition.value["live_span"]
                  # show_legend - (optional) is a type of bool
                  show_legend = heatmap_definition.value["show_legend"]
                  # time - (optional) is a type of map of string
                  time = heatmap_definition.value["time"]
                  # title - (optional) is a type of string
                  title = heatmap_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = heatmap_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = heatmap_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = heatmap_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "event" {
                    for_each = heatmap_definition.value.event
                    content {
                      # q - (required) is a type of string
                      q = event.value["q"]
                      # tags_execution - (optional) is a type of string
                      tags_execution = event.value["tags_execution"]
                    }
                  }

                  dynamic "request" {
                    for_each = heatmap_definition.value.request
                    content {
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "style" {
                        for_each = request.value.style
                        content {
                          # palette - (optional) is a type of string
                          palette = style.value["palette"]
                        }
                      }

                    }
                  }

                  dynamic "yaxis" {
                    for_each = heatmap_definition.value.yaxis
                    content {
                      # include_zero - (optional) is a type of bool
                      include_zero = yaxis.value["include_zero"]
                      # label - (optional) is a type of string
                      label = yaxis.value["label"]
                      # max - (optional) is a type of string
                      max = yaxis.value["max"]
                      # min - (optional) is a type of string
                      min = yaxis.value["min"]
                      # scale - (optional) is a type of string
                      scale = yaxis.value["scale"]
                    }
                  }

                }
              }

              dynamic "hostmap_definition" {
                for_each = widget.value.hostmap_definition
                content {
                  # group - (optional) is a type of list of string
                  group = hostmap_definition.value["group"]
                  # no_group_hosts - (optional) is a type of bool
                  no_group_hosts = hostmap_definition.value["no_group_hosts"]
                  # no_metric_hosts - (optional) is a type of bool
                  no_metric_hosts = hostmap_definition.value["no_metric_hosts"]
                  # node_type - (optional) is a type of string
                  node_type = hostmap_definition.value["node_type"]
                  # scope - (optional) is a type of list of string
                  scope = hostmap_definition.value["scope"]
                  # title - (optional) is a type of string
                  title = hostmap_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = hostmap_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = hostmap_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = hostmap_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = hostmap_definition.value.request
                    content {

                      dynamic "fill" {
                        for_each = request.value.fill
                        content {
                          # q - (optional) is a type of string
                          q = fill.value["q"]

                          dynamic "apm_query" {
                            for_each = fill.value.apm_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = apm_query.value["compute"]
                              # index - (required) is a type of string
                              index = apm_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = apm_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = apm_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = apm_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = apm_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = apm_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "log_query" {
                            for_each = fill.value.log_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = log_query.value["compute"]
                              # index - (required) is a type of string
                              index = log_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = log_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = log_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = log_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = log_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = log_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "process_query" {
                            for_each = fill.value.process_query
                            content {
                              # filter_by - (optional) is a type of list of string
                              filter_by = process_query.value["filter_by"]
                              # limit - (optional) is a type of number
                              limit = process_query.value["limit"]
                              # metric - (required) is a type of string
                              metric = process_query.value["metric"]
                              # search_by - (optional) is a type of string
                              search_by = process_query.value["search_by"]
                            }
                          }

                          dynamic "rum_query" {
                            for_each = fill.value.rum_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = rum_query.value["compute"]
                              # index - (required) is a type of string
                              index = rum_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = rum_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = rum_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = rum_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = rum_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = rum_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "security_query" {
                            for_each = fill.value.security_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = security_query.value["compute"]
                              # index - (required) is a type of string
                              index = security_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = security_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = security_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = security_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = security_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = security_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                        }
                      }

                      dynamic "size" {
                        for_each = request.value.size
                        content {
                          # q - (optional) is a type of string
                          q = size.value["q"]

                          dynamic "apm_query" {
                            for_each = size.value.apm_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = apm_query.value["compute"]
                              # index - (required) is a type of string
                              index = apm_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = apm_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = apm_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = apm_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = apm_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = apm_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "log_query" {
                            for_each = size.value.log_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = log_query.value["compute"]
                              # index - (required) is a type of string
                              index = log_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = log_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = log_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = log_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = log_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = log_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "process_query" {
                            for_each = size.value.process_query
                            content {
                              # filter_by - (optional) is a type of list of string
                              filter_by = process_query.value["filter_by"]
                              # limit - (optional) is a type of number
                              limit = process_query.value["limit"]
                              # metric - (required) is a type of string
                              metric = process_query.value["metric"]
                              # search_by - (optional) is a type of string
                              search_by = process_query.value["search_by"]
                            }
                          }

                          dynamic "rum_query" {
                            for_each = size.value.rum_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = rum_query.value["compute"]
                              # index - (required) is a type of string
                              index = rum_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = rum_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = rum_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = rum_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = rum_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = rum_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "security_query" {
                            for_each = size.value.security_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = security_query.value["compute"]
                              # index - (required) is a type of string
                              index = security_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = security_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = security_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = security_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = security_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = security_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "style" {
                    for_each = hostmap_definition.value.style
                    content {
                      # fill_max - (optional) is a type of string
                      fill_max = style.value["fill_max"]
                      # fill_min - (optional) is a type of string
                      fill_min = style.value["fill_min"]
                      # palette - (optional) is a type of string
                      palette = style.value["palette"]
                      # palette_flip - (optional) is a type of bool
                      palette_flip = style.value["palette_flip"]
                    }
                  }

                }
              }

              dynamic "iframe_definition" {
                for_each = widget.value.iframe_definition
                content {
                  # url - (required) is a type of string
                  url = iframe_definition.value["url"]
                }
              }

              dynamic "image_definition" {
                for_each = widget.value.image_definition
                content {
                  # margin - (optional) is a type of string
                  margin = image_definition.value["margin"]
                  # sizing - (optional) is a type of string
                  sizing = image_definition.value["sizing"]
                  # url - (required) is a type of string
                  url = image_definition.value["url"]
                }
              }

              dynamic "log_stream_definition" {
                for_each = widget.value.log_stream_definition
                content {
                  # columns - (optional) is a type of list of string
                  columns = log_stream_definition.value["columns"]
                  # indexes - (optional) is a type of list of string
                  indexes = log_stream_definition.value["indexes"]
                  # live_span - (optional) is a type of string
                  live_span = log_stream_definition.value["live_span"]
                  # logset - (optional) is a type of string
                  logset = log_stream_definition.value["logset"]
                  # message_display - (optional) is a type of string
                  message_display = log_stream_definition.value["message_display"]
                  # query - (optional) is a type of string
                  query = log_stream_definition.value["query"]
                  # show_date_column - (optional) is a type of bool
                  show_date_column = log_stream_definition.value["show_date_column"]
                  # show_message_column - (optional) is a type of bool
                  show_message_column = log_stream_definition.value["show_message_column"]
                  # time - (optional) is a type of map of string
                  time = log_stream_definition.value["time"]
                  # title - (optional) is a type of string
                  title = log_stream_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = log_stream_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = log_stream_definition.value["title_size"]

                  dynamic "sort" {
                    for_each = log_stream_definition.value.sort
                    content {
                      # column - (required) is a type of string
                      column = sort.value["column"]
                      # order - (required) is a type of string
                      order = sort.value["order"]
                    }
                  }

                }
              }

              dynamic "manage_status_definition" {
                for_each = widget.value.manage_status_definition
                content {
                  # color_preference - (optional) is a type of string
                  color_preference = manage_status_definition.value["color_preference"]
                  # count - (optional) is a type of number
                  count = manage_status_definition.value["count"]
                  # display_format - (optional) is a type of string
                  display_format = manage_status_definition.value["display_format"]
                  # hide_zero_counts - (optional) is a type of bool
                  hide_zero_counts = manage_status_definition.value["hide_zero_counts"]
                  # query - (required) is a type of string
                  query = manage_status_definition.value["query"]
                  # show_last_triggered - (optional) is a type of bool
                  show_last_triggered = manage_status_definition.value["show_last_triggered"]
                  # sort - (optional) is a type of string
                  sort = manage_status_definition.value["sort"]
                  # start - (optional) is a type of number
                  start = manage_status_definition.value["start"]
                  # summary_type - (optional) is a type of string
                  summary_type = manage_status_definition.value["summary_type"]
                  # title - (optional) is a type of string
                  title = manage_status_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = manage_status_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = manage_status_definition.value["title_size"]
                }
              }

              dynamic "note_definition" {
                for_each = widget.value.note_definition
                content {
                  # background_color - (optional) is a type of string
                  background_color = note_definition.value["background_color"]
                  # content - (required) is a type of string
                  content = note_definition.value["content"]
                  # font_size - (optional) is a type of string
                  font_size = note_definition.value["font_size"]
                  # show_tick - (optional) is a type of bool
                  show_tick = note_definition.value["show_tick"]
                  # text_align - (optional) is a type of string
                  text_align = note_definition.value["text_align"]
                  # tick_edge - (optional) is a type of string
                  tick_edge = note_definition.value["tick_edge"]
                  # tick_pos - (optional) is a type of string
                  tick_pos = note_definition.value["tick_pos"]
                }
              }

              dynamic "query_table_definition" {
                for_each = widget.value.query_table_definition
                content {
                  # has_search_bar - (optional) is a type of string
                  has_search_bar = query_table_definition.value["has_search_bar"]
                  # live_span - (optional) is a type of string
                  live_span = query_table_definition.value["live_span"]
                  # time - (optional) is a type of map of string
                  time = query_table_definition.value["time"]
                  # title - (optional) is a type of string
                  title = query_table_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = query_table_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = query_table_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = query_table_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = query_table_definition.value.request
                    content {
                      # aggregator - (optional) is a type of string
                      aggregator = request.value["aggregator"]
                      # alias - (optional) is a type of string
                      alias = request.value["alias"]
                      # cell_display_mode - (optional) is a type of list of string
                      cell_display_mode = request.value["cell_display_mode"]
                      # limit - (optional) is a type of number
                      limit = request.value["limit"]
                      # order - (optional) is a type of string
                      order = request.value["order"]
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "apm_stats_query" {
                        for_each = request.value.apm_stats_query
                        content {
                          # env - (required) is a type of string
                          env = apm_stats_query.value["env"]
                          # name - (required) is a type of string
                          name = apm_stats_query.value["name"]
                          # primary_tag - (required) is a type of string
                          primary_tag = apm_stats_query.value["primary_tag"]
                          # resource - (optional) is a type of string
                          resource = apm_stats_query.value["resource"]
                          # row_type - (required) is a type of string
                          row_type = apm_stats_query.value["row_type"]
                          # service - (required) is a type of string
                          service = apm_stats_query.value["service"]

                          dynamic "columns" {
                            for_each = apm_stats_query.value.columns
                            content {
                              # alias - (optional) is a type of string
                              alias = columns.value["alias"]
                              # cell_display_mode - (optional) is a type of string
                              cell_display_mode = columns.value["cell_display_mode"]
                              # name - (required) is a type of string
                              name = columns.value["name"]
                              # order - (optional) is a type of string
                              order = columns.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "conditional_formats" {
                        for_each = request.value.conditional_formats
                        content {
                          # comparator - (required) is a type of string
                          comparator = conditional_formats.value["comparator"]
                          # custom_bg_color - (optional) is a type of string
                          custom_bg_color = conditional_formats.value["custom_bg_color"]
                          # custom_fg_color - (optional) is a type of string
                          custom_fg_color = conditional_formats.value["custom_fg_color"]
                          # hide_value - (optional) is a type of bool
                          hide_value = conditional_formats.value["hide_value"]
                          # image_url - (optional) is a type of string
                          image_url = conditional_formats.value["image_url"]
                          # metric - (optional) is a type of string
                          metric = conditional_formats.value["metric"]
                          # palette - (required) is a type of string
                          palette = conditional_formats.value["palette"]
                          # timeframe - (optional) is a type of string
                          timeframe = conditional_formats.value["timeframe"]
                          # value - (required) is a type of number
                          value = conditional_formats.value["value"]
                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "query_value_definition" {
                for_each = widget.value.query_value_definition
                content {
                  # autoscale - (optional) is a type of bool
                  autoscale = query_value_definition.value["autoscale"]
                  # custom_unit - (optional) is a type of string
                  custom_unit = query_value_definition.value["custom_unit"]
                  # live_span - (optional) is a type of string
                  live_span = query_value_definition.value["live_span"]
                  # precision - (optional) is a type of number
                  precision = query_value_definition.value["precision"]
                  # text_align - (optional) is a type of string
                  text_align = query_value_definition.value["text_align"]
                  # time - (optional) is a type of map of string
                  time = query_value_definition.value["time"]
                  # title - (optional) is a type of string
                  title = query_value_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = query_value_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = query_value_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = query_value_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = query_value_definition.value.request
                    content {
                      # aggregator - (optional) is a type of string
                      aggregator = request.value["aggregator"]
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "conditional_formats" {
                        for_each = request.value.conditional_formats
                        content {
                          # comparator - (required) is a type of string
                          comparator = conditional_formats.value["comparator"]
                          # custom_bg_color - (optional) is a type of string
                          custom_bg_color = conditional_formats.value["custom_bg_color"]
                          # custom_fg_color - (optional) is a type of string
                          custom_fg_color = conditional_formats.value["custom_fg_color"]
                          # hide_value - (optional) is a type of bool
                          hide_value = conditional_formats.value["hide_value"]
                          # image_url - (optional) is a type of string
                          image_url = conditional_formats.value["image_url"]
                          # metric - (optional) is a type of string
                          metric = conditional_formats.value["metric"]
                          # palette - (required) is a type of string
                          palette = conditional_formats.value["palette"]
                          # timeframe - (optional) is a type of string
                          timeframe = conditional_formats.value["timeframe"]
                          # value - (required) is a type of number
                          value = conditional_formats.value["value"]
                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "scatterplot_definition" {
                for_each = widget.value.scatterplot_definition
                content {
                  # color_by_groups - (optional) is a type of list of string
                  color_by_groups = scatterplot_definition.value["color_by_groups"]
                  # live_span - (optional) is a type of string
                  live_span = scatterplot_definition.value["live_span"]
                  # time - (optional) is a type of map of string
                  time = scatterplot_definition.value["time"]
                  # title - (optional) is a type of string
                  title = scatterplot_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = scatterplot_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = scatterplot_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = scatterplot_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = scatterplot_definition.value.request
                    content {

                      dynamic "x" {
                        for_each = request.value.x
                        content {
                          # aggregator - (optional) is a type of string
                          aggregator = x.value["aggregator"]
                          # q - (optional) is a type of string
                          q = x.value["q"]

                          dynamic "apm_query" {
                            for_each = x.value.apm_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = apm_query.value["compute"]
                              # index - (required) is a type of string
                              index = apm_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = apm_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = apm_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = apm_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = apm_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = apm_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "log_query" {
                            for_each = x.value.log_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = log_query.value["compute"]
                              # index - (required) is a type of string
                              index = log_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = log_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = log_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = log_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = log_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = log_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "process_query" {
                            for_each = x.value.process_query
                            content {
                              # filter_by - (optional) is a type of list of string
                              filter_by = process_query.value["filter_by"]
                              # limit - (optional) is a type of number
                              limit = process_query.value["limit"]
                              # metric - (required) is a type of string
                              metric = process_query.value["metric"]
                              # search_by - (optional) is a type of string
                              search_by = process_query.value["search_by"]
                            }
                          }

                          dynamic "rum_query" {
                            for_each = x.value.rum_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = rum_query.value["compute"]
                              # index - (required) is a type of string
                              index = rum_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = rum_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = rum_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = rum_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = rum_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = rum_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "security_query" {
                            for_each = x.value.security_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = security_query.value["compute"]
                              # index - (required) is a type of string
                              index = security_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = security_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = security_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = security_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = security_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = security_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                        }
                      }

                      dynamic "y" {
                        for_each = request.value.y
                        content {
                          # aggregator - (optional) is a type of string
                          aggregator = y.value["aggregator"]
                          # q - (optional) is a type of string
                          q = y.value["q"]

                          dynamic "apm_query" {
                            for_each = y.value.apm_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = apm_query.value["compute"]
                              # index - (required) is a type of string
                              index = apm_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = apm_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = apm_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = apm_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = apm_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = apm_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "log_query" {
                            for_each = y.value.log_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = log_query.value["compute"]
                              # index - (required) is a type of string
                              index = log_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = log_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = log_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = log_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = log_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = log_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "process_query" {
                            for_each = y.value.process_query
                            content {
                              # filter_by - (optional) is a type of list of string
                              filter_by = process_query.value["filter_by"]
                              # limit - (optional) is a type of number
                              limit = process_query.value["limit"]
                              # metric - (required) is a type of string
                              metric = process_query.value["metric"]
                              # search_by - (optional) is a type of string
                              search_by = process_query.value["search_by"]
                            }
                          }

                          dynamic "rum_query" {
                            for_each = y.value.rum_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = rum_query.value["compute"]
                              # index - (required) is a type of string
                              index = rum_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = rum_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = rum_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = rum_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = rum_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = rum_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                          dynamic "security_query" {
                            for_each = y.value.security_query
                            content {
                              # compute - (optional) is a type of map of string
                              compute = security_query.value["compute"]
                              # index - (required) is a type of string
                              index = security_query.value["index"]
                              # search - (optional) is a type of map of string
                              search = security_query.value["search"]
                              # search_query - (optional) is a type of string
                              search_query = security_query.value["search_query"]

                              dynamic "compute_query" {
                                for_each = security_query.value.compute_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = compute_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = compute_query.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = compute_query.value["interval"]
                                }
                              }

                              dynamic "group_by" {
                                for_each = security_query.value.group_by
                                content {
                                  # facet - (optional) is a type of string
                                  facet = group_by.value["facet"]
                                  # limit - (optional) is a type of number
                                  limit = group_by.value["limit"]
                                  # sort - (optional) is a type of map of string
                                  sort = group_by.value["sort"]

                                  dynamic "sort_query" {
                                    for_each = group_by.value.sort_query
                                    content {
                                      # aggregation - (required) is a type of string
                                      aggregation = sort_query.value["aggregation"]
                                      # facet - (optional) is a type of string
                                      facet = sort_query.value["facet"]
                                      # order - (required) is a type of string
                                      order = sort_query.value["order"]
                                    }
                                  }

                                }
                              }

                              dynamic "multi_compute" {
                                for_each = security_query.value.multi_compute
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = multi_compute.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = multi_compute.value["facet"]
                                  # interval - (optional) is a type of number
                                  interval = multi_compute.value["interval"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "xaxis" {
                    for_each = scatterplot_definition.value.xaxis
                    content {
                      # include_zero - (optional) is a type of bool
                      include_zero = xaxis.value["include_zero"]
                      # label - (optional) is a type of string
                      label = xaxis.value["label"]
                      # max - (optional) is a type of string
                      max = xaxis.value["max"]
                      # min - (optional) is a type of string
                      min = xaxis.value["min"]
                      # scale - (optional) is a type of string
                      scale = xaxis.value["scale"]
                    }
                  }

                  dynamic "yaxis" {
                    for_each = scatterplot_definition.value.yaxis
                    content {
                      # include_zero - (optional) is a type of bool
                      include_zero = yaxis.value["include_zero"]
                      # label - (optional) is a type of string
                      label = yaxis.value["label"]
                      # max - (optional) is a type of string
                      max = yaxis.value["max"]
                      # min - (optional) is a type of string
                      min = yaxis.value["min"]
                      # scale - (optional) is a type of string
                      scale = yaxis.value["scale"]
                    }
                  }

                }
              }

              dynamic "service_level_objective_definition" {
                for_each = widget.value.service_level_objective_definition
                content {
                  # show_error_budget - (optional) is a type of bool
                  show_error_budget = service_level_objective_definition.value["show_error_budget"]
                  # slo_id - (required) is a type of string
                  slo_id = service_level_objective_definition.value["slo_id"]
                  # time_windows - (required) is a type of list of string
                  time_windows = service_level_objective_definition.value["time_windows"]
                  # title - (optional) is a type of string
                  title = service_level_objective_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = service_level_objective_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = service_level_objective_definition.value["title_size"]
                  # view_mode - (required) is a type of string
                  view_mode = service_level_objective_definition.value["view_mode"]
                  # view_type - (required) is a type of string
                  view_type = service_level_objective_definition.value["view_type"]
                }
              }

              dynamic "servicemap_definition" {
                for_each = widget.value.servicemap_definition
                content {
                  # filters - (required) is a type of list of string
                  filters = servicemap_definition.value["filters"]
                  # service - (required) is a type of string
                  service = servicemap_definition.value["service"]
                  # title - (optional) is a type of string
                  title = servicemap_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = servicemap_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = servicemap_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = servicemap_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                }
              }

              dynamic "timeseries_definition" {
                for_each = widget.value.timeseries_definition
                content {
                  # legend_columns - (optional) is a type of set of string
                  legend_columns = timeseries_definition.value["legend_columns"]
                  # legend_layout - (optional) is a type of string
                  legend_layout = timeseries_definition.value["legend_layout"]
                  # legend_size - (optional) is a type of string
                  legend_size = timeseries_definition.value["legend_size"]
                  # live_span - (optional) is a type of string
                  live_span = timeseries_definition.value["live_span"]
                  # show_legend - (optional) is a type of bool
                  show_legend = timeseries_definition.value["show_legend"]
                  # time - (optional) is a type of map of string
                  time = timeseries_definition.value["time"]
                  # title - (optional) is a type of string
                  title = timeseries_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = timeseries_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = timeseries_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = timeseries_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "event" {
                    for_each = timeseries_definition.value.event
                    content {
                      # q - (required) is a type of string
                      q = event.value["q"]
                      # tags_execution - (optional) is a type of string
                      tags_execution = event.value["tags_execution"]
                    }
                  }

                  dynamic "marker" {
                    for_each = timeseries_definition.value.marker
                    content {
                      # display_type - (optional) is a type of string
                      display_type = marker.value["display_type"]
                      # label - (optional) is a type of string
                      label = marker.value["label"]
                      # value - (required) is a type of string
                      value = marker.value["value"]
                    }
                  }

                  dynamic "request" {
                    for_each = timeseries_definition.value.request
                    content {
                      # display_type - (optional) is a type of string
                      display_type = request.value["display_type"]
                      # on_right_yaxis - (optional) is a type of bool
                      on_right_yaxis = request.value["on_right_yaxis"]
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "metadata" {
                        for_each = request.value.metadata
                        content {
                          # alias_name - (optional) is a type of string
                          alias_name = metadata.value["alias_name"]
                          # expression - (required) is a type of string
                          expression = metadata.value["expression"]
                        }
                      }

                      dynamic "network_query" {
                        for_each = request.value.network_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = network_query.value["compute"]
                          # index - (required) is a type of string
                          index = network_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = network_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = network_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = network_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = network_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = network_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "style" {
                        for_each = request.value.style
                        content {
                          # line_type - (optional) is a type of string
                          line_type = style.value["line_type"]
                          # line_width - (optional) is a type of string
                          line_width = style.value["line_width"]
                          # palette - (optional) is a type of string
                          palette = style.value["palette"]
                        }
                      }

                    }
                  }

                  dynamic "right_yaxis" {
                    for_each = timeseries_definition.value.right_yaxis
                    content {
                      # include_zero - (optional) is a type of bool
                      include_zero = right_yaxis.value["include_zero"]
                      # label - (optional) is a type of string
                      label = right_yaxis.value["label"]
                      # max - (optional) is a type of string
                      max = right_yaxis.value["max"]
                      # min - (optional) is a type of string
                      min = right_yaxis.value["min"]
                      # scale - (optional) is a type of string
                      scale = right_yaxis.value["scale"]
                    }
                  }

                  dynamic "yaxis" {
                    for_each = timeseries_definition.value.yaxis
                    content {
                      # include_zero - (optional) is a type of bool
                      include_zero = yaxis.value["include_zero"]
                      # label - (optional) is a type of string
                      label = yaxis.value["label"]
                      # max - (optional) is a type of string
                      max = yaxis.value["max"]
                      # min - (optional) is a type of string
                      min = yaxis.value["min"]
                      # scale - (optional) is a type of string
                      scale = yaxis.value["scale"]
                    }
                  }

                }
              }

              dynamic "toplist_definition" {
                for_each = widget.value.toplist_definition
                content {
                  # live_span - (optional) is a type of string
                  live_span = toplist_definition.value["live_span"]
                  # time - (optional) is a type of map of string
                  time = toplist_definition.value["time"]
                  # title - (optional) is a type of string
                  title = toplist_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = toplist_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = toplist_definition.value["title_size"]

                  dynamic "custom_link" {
                    for_each = toplist_definition.value.custom_link
                    content {
                      # label - (required) is a type of string
                      label = custom_link.value["label"]
                      # link - (required) is a type of string
                      link = custom_link.value["link"]
                    }
                  }

                  dynamic "request" {
                    for_each = toplist_definition.value.request
                    content {
                      # q - (optional) is a type of string
                      q = request.value["q"]

                      dynamic "apm_query" {
                        for_each = request.value.apm_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = apm_query.value["compute"]
                          # index - (required) is a type of string
                          index = apm_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = apm_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = apm_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = apm_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = apm_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = apm_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "conditional_formats" {
                        for_each = request.value.conditional_formats
                        content {
                          # comparator - (required) is a type of string
                          comparator = conditional_formats.value["comparator"]
                          # custom_bg_color - (optional) is a type of string
                          custom_bg_color = conditional_formats.value["custom_bg_color"]
                          # custom_fg_color - (optional) is a type of string
                          custom_fg_color = conditional_formats.value["custom_fg_color"]
                          # hide_value - (optional) is a type of bool
                          hide_value = conditional_formats.value["hide_value"]
                          # image_url - (optional) is a type of string
                          image_url = conditional_formats.value["image_url"]
                          # metric - (optional) is a type of string
                          metric = conditional_formats.value["metric"]
                          # palette - (required) is a type of string
                          palette = conditional_formats.value["palette"]
                          # timeframe - (optional) is a type of string
                          timeframe = conditional_formats.value["timeframe"]
                          # value - (required) is a type of number
                          value = conditional_formats.value["value"]
                        }
                      }

                      dynamic "log_query" {
                        for_each = request.value.log_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = log_query.value["compute"]
                          # index - (required) is a type of string
                          index = log_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = log_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = log_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = log_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = log_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = log_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "process_query" {
                        for_each = request.value.process_query
                        content {
                          # filter_by - (optional) is a type of list of string
                          filter_by = process_query.value["filter_by"]
                          # limit - (optional) is a type of number
                          limit = process_query.value["limit"]
                          # metric - (required) is a type of string
                          metric = process_query.value["metric"]
                          # search_by - (optional) is a type of string
                          search_by = process_query.value["search_by"]
                        }
                      }

                      dynamic "rum_query" {
                        for_each = request.value.rum_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = rum_query.value["compute"]
                          # index - (required) is a type of string
                          index = rum_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = rum_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = rum_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = rum_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = rum_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = rum_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "security_query" {
                        for_each = request.value.security_query
                        content {
                          # compute - (optional) is a type of map of string
                          compute = security_query.value["compute"]
                          # index - (required) is a type of string
                          index = security_query.value["index"]
                          # search - (optional) is a type of map of string
                          search = security_query.value["search"]
                          # search_query - (optional) is a type of string
                          search_query = security_query.value["search_query"]

                          dynamic "compute_query" {
                            for_each = security_query.value.compute_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = compute_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = compute_query.value["facet"]
                              # interval - (optional) is a type of number
                              interval = compute_query.value["interval"]
                            }
                          }

                          dynamic "group_by" {
                            for_each = security_query.value.group_by
                            content {
                              # facet - (optional) is a type of string
                              facet = group_by.value["facet"]
                              # limit - (optional) is a type of number
                              limit = group_by.value["limit"]
                              # sort - (optional) is a type of map of string
                              sort = group_by.value["sort"]

                              dynamic "sort_query" {
                                for_each = group_by.value.sort_query
                                content {
                                  # aggregation - (required) is a type of string
                                  aggregation = sort_query.value["aggregation"]
                                  # facet - (optional) is a type of string
                                  facet = sort_query.value["facet"]
                                  # order - (required) is a type of string
                                  order = sort_query.value["order"]
                                }
                              }

                            }
                          }

                          dynamic "multi_compute" {
                            for_each = security_query.value.multi_compute
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = multi_compute.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = multi_compute.value["facet"]
                              # interval - (optional) is a type of number
                              interval = multi_compute.value["interval"]
                            }
                          }

                        }
                      }

                      dynamic "style" {
                        for_each = request.value.style
                        content {
                          # palette - (optional) is a type of string
                          palette = style.value["palette"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "trace_service_definition" {
                for_each = widget.value.trace_service_definition
                content {
                  # display_format - (optional) is a type of string
                  display_format = trace_service_definition.value["display_format"]
                  # env - (required) is a type of string
                  env = trace_service_definition.value["env"]
                  # live_span - (optional) is a type of string
                  live_span = trace_service_definition.value["live_span"]
                  # service - (required) is a type of string
                  service = trace_service_definition.value["service"]
                  # show_breakdown - (optional) is a type of bool
                  show_breakdown = trace_service_definition.value["show_breakdown"]
                  # show_distribution - (optional) is a type of bool
                  show_distribution = trace_service_definition.value["show_distribution"]
                  # show_errors - (optional) is a type of bool
                  show_errors = trace_service_definition.value["show_errors"]
                  # show_hits - (optional) is a type of bool
                  show_hits = trace_service_definition.value["show_hits"]
                  # show_latency - (optional) is a type of bool
                  show_latency = trace_service_definition.value["show_latency"]
                  # show_resource_list - (optional) is a type of bool
                  show_resource_list = trace_service_definition.value["show_resource_list"]
                  # size_format - (optional) is a type of string
                  size_format = trace_service_definition.value["size_format"]
                  # span_name - (required) is a type of string
                  span_name = trace_service_definition.value["span_name"]
                  # time - (optional) is a type of map of string
                  time = trace_service_definition.value["time"]
                  # title - (optional) is a type of string
                  title = trace_service_definition.value["title"]
                  # title_align - (optional) is a type of string
                  title_align = trace_service_definition.value["title_align"]
                  # title_size - (optional) is a type of string
                  title_size = trace_service_definition.value["title_size"]
                }
              }

              dynamic "widget_layout" {
                for_each = widget.value.widget_layout
                content {
                  # height - (required) is a type of number
                  height = widget_layout.value["height"]
                  # width - (required) is a type of number
                  width = widget_layout.value["width"]
                  # x - (required) is a type of number
                  x = widget_layout.value["x"]
                  # y - (required) is a type of number
                  y = widget_layout.value["y"]
                }
              }

            }
          }

        }
      }

      dynamic "heatmap_definition" {
        for_each = widget.value.heatmap_definition
        content {
          # legend_size - (optional) is a type of string
          legend_size = heatmap_definition.value["legend_size"]
          # live_span - (optional) is a type of string
          live_span = heatmap_definition.value["live_span"]
          # show_legend - (optional) is a type of bool
          show_legend = heatmap_definition.value["show_legend"]
          # time - (optional) is a type of map of string
          time = heatmap_definition.value["time"]
          # title - (optional) is a type of string
          title = heatmap_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = heatmap_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = heatmap_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = heatmap_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "event" {
            for_each = heatmap_definition.value.event
            content {
              # q - (required) is a type of string
              q = event.value["q"]
              # tags_execution - (optional) is a type of string
              tags_execution = event.value["tags_execution"]
            }
          }

          dynamic "request" {
            for_each = heatmap_definition.value.request
            content {
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "style" {
                for_each = request.value.style
                content {
                  # palette - (optional) is a type of string
                  palette = style.value["palette"]
                }
              }

            }
          }

          dynamic "yaxis" {
            for_each = heatmap_definition.value.yaxis
            content {
              # include_zero - (optional) is a type of bool
              include_zero = yaxis.value["include_zero"]
              # label - (optional) is a type of string
              label = yaxis.value["label"]
              # max - (optional) is a type of string
              max = yaxis.value["max"]
              # min - (optional) is a type of string
              min = yaxis.value["min"]
              # scale - (optional) is a type of string
              scale = yaxis.value["scale"]
            }
          }

        }
      }

      dynamic "hostmap_definition" {
        for_each = widget.value.hostmap_definition
        content {
          # group - (optional) is a type of list of string
          group = hostmap_definition.value["group"]
          # no_group_hosts - (optional) is a type of bool
          no_group_hosts = hostmap_definition.value["no_group_hosts"]
          # no_metric_hosts - (optional) is a type of bool
          no_metric_hosts = hostmap_definition.value["no_metric_hosts"]
          # node_type - (optional) is a type of string
          node_type = hostmap_definition.value["node_type"]
          # scope - (optional) is a type of list of string
          scope = hostmap_definition.value["scope"]
          # title - (optional) is a type of string
          title = hostmap_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = hostmap_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = hostmap_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = hostmap_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = hostmap_definition.value.request
            content {

              dynamic "fill" {
                for_each = request.value.fill
                content {
                  # q - (optional) is a type of string
                  q = fill.value["q"]

                  dynamic "apm_query" {
                    for_each = fill.value.apm_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = apm_query.value["compute"]
                      # index - (required) is a type of string
                      index = apm_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = apm_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = apm_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = apm_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = apm_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = apm_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "log_query" {
                    for_each = fill.value.log_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = log_query.value["compute"]
                      # index - (required) is a type of string
                      index = log_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = log_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = log_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = log_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = log_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = log_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "process_query" {
                    for_each = fill.value.process_query
                    content {
                      # filter_by - (optional) is a type of list of string
                      filter_by = process_query.value["filter_by"]
                      # limit - (optional) is a type of number
                      limit = process_query.value["limit"]
                      # metric - (required) is a type of string
                      metric = process_query.value["metric"]
                      # search_by - (optional) is a type of string
                      search_by = process_query.value["search_by"]
                    }
                  }

                  dynamic "rum_query" {
                    for_each = fill.value.rum_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = rum_query.value["compute"]
                      # index - (required) is a type of string
                      index = rum_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = rum_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = rum_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = rum_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = rum_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = rum_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "security_query" {
                    for_each = fill.value.security_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = security_query.value["compute"]
                      # index - (required) is a type of string
                      index = security_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = security_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = security_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = security_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = security_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = security_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "size" {
                for_each = request.value.size
                content {
                  # q - (optional) is a type of string
                  q = size.value["q"]

                  dynamic "apm_query" {
                    for_each = size.value.apm_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = apm_query.value["compute"]
                      # index - (required) is a type of string
                      index = apm_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = apm_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = apm_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = apm_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = apm_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = apm_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "log_query" {
                    for_each = size.value.log_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = log_query.value["compute"]
                      # index - (required) is a type of string
                      index = log_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = log_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = log_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = log_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = log_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = log_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "process_query" {
                    for_each = size.value.process_query
                    content {
                      # filter_by - (optional) is a type of list of string
                      filter_by = process_query.value["filter_by"]
                      # limit - (optional) is a type of number
                      limit = process_query.value["limit"]
                      # metric - (required) is a type of string
                      metric = process_query.value["metric"]
                      # search_by - (optional) is a type of string
                      search_by = process_query.value["search_by"]
                    }
                  }

                  dynamic "rum_query" {
                    for_each = size.value.rum_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = rum_query.value["compute"]
                      # index - (required) is a type of string
                      index = rum_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = rum_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = rum_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = rum_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = rum_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = rum_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "security_query" {
                    for_each = size.value.security_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = security_query.value["compute"]
                      # index - (required) is a type of string
                      index = security_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = security_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = security_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = security_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = security_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = security_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "style" {
            for_each = hostmap_definition.value.style
            content {
              # fill_max - (optional) is a type of string
              fill_max = style.value["fill_max"]
              # fill_min - (optional) is a type of string
              fill_min = style.value["fill_min"]
              # palette - (optional) is a type of string
              palette = style.value["palette"]
              # palette_flip - (optional) is a type of bool
              palette_flip = style.value["palette_flip"]
            }
          }

        }
      }

      dynamic "iframe_definition" {
        for_each = widget.value.iframe_definition
        content {
          # url - (required) is a type of string
          url = iframe_definition.value["url"]
        }
      }

      dynamic "image_definition" {
        for_each = widget.value.image_definition
        content {
          # margin - (optional) is a type of string
          margin = image_definition.value["margin"]
          # sizing - (optional) is a type of string
          sizing = image_definition.value["sizing"]
          # url - (required) is a type of string
          url = image_definition.value["url"]
        }
      }

      dynamic "log_stream_definition" {
        for_each = widget.value.log_stream_definition
        content {
          # columns - (optional) is a type of list of string
          columns = log_stream_definition.value["columns"]
          # indexes - (optional) is a type of list of string
          indexes = log_stream_definition.value["indexes"]
          # live_span - (optional) is a type of string
          live_span = log_stream_definition.value["live_span"]
          # logset - (optional) is a type of string
          logset = log_stream_definition.value["logset"]
          # message_display - (optional) is a type of string
          message_display = log_stream_definition.value["message_display"]
          # query - (optional) is a type of string
          query = log_stream_definition.value["query"]
          # show_date_column - (optional) is a type of bool
          show_date_column = log_stream_definition.value["show_date_column"]
          # show_message_column - (optional) is a type of bool
          show_message_column = log_stream_definition.value["show_message_column"]
          # time - (optional) is a type of map of string
          time = log_stream_definition.value["time"]
          # title - (optional) is a type of string
          title = log_stream_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = log_stream_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = log_stream_definition.value["title_size"]

          dynamic "sort" {
            for_each = log_stream_definition.value.sort
            content {
              # column - (required) is a type of string
              column = sort.value["column"]
              # order - (required) is a type of string
              order = sort.value["order"]
            }
          }

        }
      }

      dynamic "manage_status_definition" {
        for_each = widget.value.manage_status_definition
        content {
          # color_preference - (optional) is a type of string
          color_preference = manage_status_definition.value["color_preference"]
          # count - (optional) is a type of number
          count = manage_status_definition.value["count"]
          # display_format - (optional) is a type of string
          display_format = manage_status_definition.value["display_format"]
          # hide_zero_counts - (optional) is a type of bool
          hide_zero_counts = manage_status_definition.value["hide_zero_counts"]
          # query - (required) is a type of string
          query = manage_status_definition.value["query"]
          # show_last_triggered - (optional) is a type of bool
          show_last_triggered = manage_status_definition.value["show_last_triggered"]
          # sort - (optional) is a type of string
          sort = manage_status_definition.value["sort"]
          # start - (optional) is a type of number
          start = manage_status_definition.value["start"]
          # summary_type - (optional) is a type of string
          summary_type = manage_status_definition.value["summary_type"]
          # title - (optional) is a type of string
          title = manage_status_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = manage_status_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = manage_status_definition.value["title_size"]
        }
      }

      dynamic "note_definition" {
        for_each = widget.value.note_definition
        content {
          # background_color - (optional) is a type of string
          background_color = note_definition.value["background_color"]
          # content - (required) is a type of string
          content = note_definition.value["content"]
          # font_size - (optional) is a type of string
          font_size = note_definition.value["font_size"]
          # show_tick - (optional) is a type of bool
          show_tick = note_definition.value["show_tick"]
          # text_align - (optional) is a type of string
          text_align = note_definition.value["text_align"]
          # tick_edge - (optional) is a type of string
          tick_edge = note_definition.value["tick_edge"]
          # tick_pos - (optional) is a type of string
          tick_pos = note_definition.value["tick_pos"]
        }
      }

      dynamic "query_table_definition" {
        for_each = widget.value.query_table_definition
        content {
          # has_search_bar - (optional) is a type of string
          has_search_bar = query_table_definition.value["has_search_bar"]
          # live_span - (optional) is a type of string
          live_span = query_table_definition.value["live_span"]
          # time - (optional) is a type of map of string
          time = query_table_definition.value["time"]
          # title - (optional) is a type of string
          title = query_table_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = query_table_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = query_table_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = query_table_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = query_table_definition.value.request
            content {
              # aggregator - (optional) is a type of string
              aggregator = request.value["aggregator"]
              # alias - (optional) is a type of string
              alias = request.value["alias"]
              # cell_display_mode - (optional) is a type of list of string
              cell_display_mode = request.value["cell_display_mode"]
              # limit - (optional) is a type of number
              limit = request.value["limit"]
              # order - (optional) is a type of string
              order = request.value["order"]
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "apm_stats_query" {
                for_each = request.value.apm_stats_query
                content {
                  # env - (required) is a type of string
                  env = apm_stats_query.value["env"]
                  # name - (required) is a type of string
                  name = apm_stats_query.value["name"]
                  # primary_tag - (required) is a type of string
                  primary_tag = apm_stats_query.value["primary_tag"]
                  # resource - (optional) is a type of string
                  resource = apm_stats_query.value["resource"]
                  # row_type - (required) is a type of string
                  row_type = apm_stats_query.value["row_type"]
                  # service - (required) is a type of string
                  service = apm_stats_query.value["service"]

                  dynamic "columns" {
                    for_each = apm_stats_query.value.columns
                    content {
                      # alias - (optional) is a type of string
                      alias = columns.value["alias"]
                      # cell_display_mode - (optional) is a type of string
                      cell_display_mode = columns.value["cell_display_mode"]
                      # name - (required) is a type of string
                      name = columns.value["name"]
                      # order - (optional) is a type of string
                      order = columns.value["order"]
                    }
                  }

                }
              }

              dynamic "conditional_formats" {
                for_each = request.value.conditional_formats
                content {
                  # comparator - (required) is a type of string
                  comparator = conditional_formats.value["comparator"]
                  # custom_bg_color - (optional) is a type of string
                  custom_bg_color = conditional_formats.value["custom_bg_color"]
                  # custom_fg_color - (optional) is a type of string
                  custom_fg_color = conditional_formats.value["custom_fg_color"]
                  # hide_value - (optional) is a type of bool
                  hide_value = conditional_formats.value["hide_value"]
                  # image_url - (optional) is a type of string
                  image_url = conditional_formats.value["image_url"]
                  # metric - (optional) is a type of string
                  metric = conditional_formats.value["metric"]
                  # palette - (required) is a type of string
                  palette = conditional_formats.value["palette"]
                  # timeframe - (optional) is a type of string
                  timeframe = conditional_formats.value["timeframe"]
                  # value - (required) is a type of number
                  value = conditional_formats.value["value"]
                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "query_value_definition" {
        for_each = widget.value.query_value_definition
        content {
          # autoscale - (optional) is a type of bool
          autoscale = query_value_definition.value["autoscale"]
          # custom_unit - (optional) is a type of string
          custom_unit = query_value_definition.value["custom_unit"]
          # live_span - (optional) is a type of string
          live_span = query_value_definition.value["live_span"]
          # precision - (optional) is a type of number
          precision = query_value_definition.value["precision"]
          # text_align - (optional) is a type of string
          text_align = query_value_definition.value["text_align"]
          # time - (optional) is a type of map of string
          time = query_value_definition.value["time"]
          # title - (optional) is a type of string
          title = query_value_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = query_value_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = query_value_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = query_value_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = query_value_definition.value.request
            content {
              # aggregator - (optional) is a type of string
              aggregator = request.value["aggregator"]
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "conditional_formats" {
                for_each = request.value.conditional_formats
                content {
                  # comparator - (required) is a type of string
                  comparator = conditional_formats.value["comparator"]
                  # custom_bg_color - (optional) is a type of string
                  custom_bg_color = conditional_formats.value["custom_bg_color"]
                  # custom_fg_color - (optional) is a type of string
                  custom_fg_color = conditional_formats.value["custom_fg_color"]
                  # hide_value - (optional) is a type of bool
                  hide_value = conditional_formats.value["hide_value"]
                  # image_url - (optional) is a type of string
                  image_url = conditional_formats.value["image_url"]
                  # metric - (optional) is a type of string
                  metric = conditional_formats.value["metric"]
                  # palette - (required) is a type of string
                  palette = conditional_formats.value["palette"]
                  # timeframe - (optional) is a type of string
                  timeframe = conditional_formats.value["timeframe"]
                  # value - (required) is a type of number
                  value = conditional_formats.value["value"]
                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "scatterplot_definition" {
        for_each = widget.value.scatterplot_definition
        content {
          # color_by_groups - (optional) is a type of list of string
          color_by_groups = scatterplot_definition.value["color_by_groups"]
          # live_span - (optional) is a type of string
          live_span = scatterplot_definition.value["live_span"]
          # time - (optional) is a type of map of string
          time = scatterplot_definition.value["time"]
          # title - (optional) is a type of string
          title = scatterplot_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = scatterplot_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = scatterplot_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = scatterplot_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = scatterplot_definition.value.request
            content {

              dynamic "x" {
                for_each = request.value.x
                content {
                  # aggregator - (optional) is a type of string
                  aggregator = x.value["aggregator"]
                  # q - (optional) is a type of string
                  q = x.value["q"]

                  dynamic "apm_query" {
                    for_each = x.value.apm_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = apm_query.value["compute"]
                      # index - (required) is a type of string
                      index = apm_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = apm_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = apm_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = apm_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = apm_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = apm_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "log_query" {
                    for_each = x.value.log_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = log_query.value["compute"]
                      # index - (required) is a type of string
                      index = log_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = log_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = log_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = log_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = log_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = log_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "process_query" {
                    for_each = x.value.process_query
                    content {
                      # filter_by - (optional) is a type of list of string
                      filter_by = process_query.value["filter_by"]
                      # limit - (optional) is a type of number
                      limit = process_query.value["limit"]
                      # metric - (required) is a type of string
                      metric = process_query.value["metric"]
                      # search_by - (optional) is a type of string
                      search_by = process_query.value["search_by"]
                    }
                  }

                  dynamic "rum_query" {
                    for_each = x.value.rum_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = rum_query.value["compute"]
                      # index - (required) is a type of string
                      index = rum_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = rum_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = rum_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = rum_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = rum_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = rum_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "security_query" {
                    for_each = x.value.security_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = security_query.value["compute"]
                      # index - (required) is a type of string
                      index = security_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = security_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = security_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = security_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = security_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = security_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "y" {
                for_each = request.value.y
                content {
                  # aggregator - (optional) is a type of string
                  aggregator = y.value["aggregator"]
                  # q - (optional) is a type of string
                  q = y.value["q"]

                  dynamic "apm_query" {
                    for_each = y.value.apm_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = apm_query.value["compute"]
                      # index - (required) is a type of string
                      index = apm_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = apm_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = apm_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = apm_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = apm_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = apm_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "log_query" {
                    for_each = y.value.log_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = log_query.value["compute"]
                      # index - (required) is a type of string
                      index = log_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = log_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = log_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = log_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = log_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = log_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "process_query" {
                    for_each = y.value.process_query
                    content {
                      # filter_by - (optional) is a type of list of string
                      filter_by = process_query.value["filter_by"]
                      # limit - (optional) is a type of number
                      limit = process_query.value["limit"]
                      # metric - (required) is a type of string
                      metric = process_query.value["metric"]
                      # search_by - (optional) is a type of string
                      search_by = process_query.value["search_by"]
                    }
                  }

                  dynamic "rum_query" {
                    for_each = y.value.rum_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = rum_query.value["compute"]
                      # index - (required) is a type of string
                      index = rum_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = rum_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = rum_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = rum_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = rum_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = rum_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                  dynamic "security_query" {
                    for_each = y.value.security_query
                    content {
                      # compute - (optional) is a type of map of string
                      compute = security_query.value["compute"]
                      # index - (required) is a type of string
                      index = security_query.value["index"]
                      # search - (optional) is a type of map of string
                      search = security_query.value["search"]
                      # search_query - (optional) is a type of string
                      search_query = security_query.value["search_query"]

                      dynamic "compute_query" {
                        for_each = security_query.value.compute_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = compute_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = compute_query.value["facet"]
                          # interval - (optional) is a type of number
                          interval = compute_query.value["interval"]
                        }
                      }

                      dynamic "group_by" {
                        for_each = security_query.value.group_by
                        content {
                          # facet - (optional) is a type of string
                          facet = group_by.value["facet"]
                          # limit - (optional) is a type of number
                          limit = group_by.value["limit"]
                          # sort - (optional) is a type of map of string
                          sort = group_by.value["sort"]

                          dynamic "sort_query" {
                            for_each = group_by.value.sort_query
                            content {
                              # aggregation - (required) is a type of string
                              aggregation = sort_query.value["aggregation"]
                              # facet - (optional) is a type of string
                              facet = sort_query.value["facet"]
                              # order - (required) is a type of string
                              order = sort_query.value["order"]
                            }
                          }

                        }
                      }

                      dynamic "multi_compute" {
                        for_each = security_query.value.multi_compute
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = multi_compute.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = multi_compute.value["facet"]
                          # interval - (optional) is a type of number
                          interval = multi_compute.value["interval"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "xaxis" {
            for_each = scatterplot_definition.value.xaxis
            content {
              # include_zero - (optional) is a type of bool
              include_zero = xaxis.value["include_zero"]
              # label - (optional) is a type of string
              label = xaxis.value["label"]
              # max - (optional) is a type of string
              max = xaxis.value["max"]
              # min - (optional) is a type of string
              min = xaxis.value["min"]
              # scale - (optional) is a type of string
              scale = xaxis.value["scale"]
            }
          }

          dynamic "yaxis" {
            for_each = scatterplot_definition.value.yaxis
            content {
              # include_zero - (optional) is a type of bool
              include_zero = yaxis.value["include_zero"]
              # label - (optional) is a type of string
              label = yaxis.value["label"]
              # max - (optional) is a type of string
              max = yaxis.value["max"]
              # min - (optional) is a type of string
              min = yaxis.value["min"]
              # scale - (optional) is a type of string
              scale = yaxis.value["scale"]
            }
          }

        }
      }

      dynamic "service_level_objective_definition" {
        for_each = widget.value.service_level_objective_definition
        content {
          # show_error_budget - (optional) is a type of bool
          show_error_budget = service_level_objective_definition.value["show_error_budget"]
          # slo_id - (required) is a type of string
          slo_id = service_level_objective_definition.value["slo_id"]
          # time_windows - (required) is a type of list of string
          time_windows = service_level_objective_definition.value["time_windows"]
          # title - (optional) is a type of string
          title = service_level_objective_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = service_level_objective_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = service_level_objective_definition.value["title_size"]
          # view_mode - (required) is a type of string
          view_mode = service_level_objective_definition.value["view_mode"]
          # view_type - (required) is a type of string
          view_type = service_level_objective_definition.value["view_type"]
        }
      }

      dynamic "servicemap_definition" {
        for_each = widget.value.servicemap_definition
        content {
          # filters - (required) is a type of list of string
          filters = servicemap_definition.value["filters"]
          # service - (required) is a type of string
          service = servicemap_definition.value["service"]
          # title - (optional) is a type of string
          title = servicemap_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = servicemap_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = servicemap_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = servicemap_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

        }
      }

      dynamic "timeseries_definition" {
        for_each = widget.value.timeseries_definition
        content {
          # legend_columns - (optional) is a type of set of string
          legend_columns = timeseries_definition.value["legend_columns"]
          # legend_layout - (optional) is a type of string
          legend_layout = timeseries_definition.value["legend_layout"]
          # legend_size - (optional) is a type of string
          legend_size = timeseries_definition.value["legend_size"]
          # live_span - (optional) is a type of string
          live_span = timeseries_definition.value["live_span"]
          # show_legend - (optional) is a type of bool
          show_legend = timeseries_definition.value["show_legend"]
          # time - (optional) is a type of map of string
          time = timeseries_definition.value["time"]
          # title - (optional) is a type of string
          title = timeseries_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = timeseries_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = timeseries_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = timeseries_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "event" {
            for_each = timeseries_definition.value.event
            content {
              # q - (required) is a type of string
              q = event.value["q"]
              # tags_execution - (optional) is a type of string
              tags_execution = event.value["tags_execution"]
            }
          }

          dynamic "marker" {
            for_each = timeseries_definition.value.marker
            content {
              # display_type - (optional) is a type of string
              display_type = marker.value["display_type"]
              # label - (optional) is a type of string
              label = marker.value["label"]
              # value - (required) is a type of string
              value = marker.value["value"]
            }
          }

          dynamic "request" {
            for_each = timeseries_definition.value.request
            content {
              # display_type - (optional) is a type of string
              display_type = request.value["display_type"]
              # on_right_yaxis - (optional) is a type of bool
              on_right_yaxis = request.value["on_right_yaxis"]
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "metadata" {
                for_each = request.value.metadata
                content {
                  # alias_name - (optional) is a type of string
                  alias_name = metadata.value["alias_name"]
                  # expression - (required) is a type of string
                  expression = metadata.value["expression"]
                }
              }

              dynamic "network_query" {
                for_each = request.value.network_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = network_query.value["compute"]
                  # index - (required) is a type of string
                  index = network_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = network_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = network_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = network_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = network_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = network_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "style" {
                for_each = request.value.style
                content {
                  # line_type - (optional) is a type of string
                  line_type = style.value["line_type"]
                  # line_width - (optional) is a type of string
                  line_width = style.value["line_width"]
                  # palette - (optional) is a type of string
                  palette = style.value["palette"]
                }
              }

            }
          }

          dynamic "right_yaxis" {
            for_each = timeseries_definition.value.right_yaxis
            content {
              # include_zero - (optional) is a type of bool
              include_zero = right_yaxis.value["include_zero"]
              # label - (optional) is a type of string
              label = right_yaxis.value["label"]
              # max - (optional) is a type of string
              max = right_yaxis.value["max"]
              # min - (optional) is a type of string
              min = right_yaxis.value["min"]
              # scale - (optional) is a type of string
              scale = right_yaxis.value["scale"]
            }
          }

          dynamic "yaxis" {
            for_each = timeseries_definition.value.yaxis
            content {
              # include_zero - (optional) is a type of bool
              include_zero = yaxis.value["include_zero"]
              # label - (optional) is a type of string
              label = yaxis.value["label"]
              # max - (optional) is a type of string
              max = yaxis.value["max"]
              # min - (optional) is a type of string
              min = yaxis.value["min"]
              # scale - (optional) is a type of string
              scale = yaxis.value["scale"]
            }
          }

        }
      }

      dynamic "toplist_definition" {
        for_each = widget.value.toplist_definition
        content {
          # live_span - (optional) is a type of string
          live_span = toplist_definition.value["live_span"]
          # time - (optional) is a type of map of string
          time = toplist_definition.value["time"]
          # title - (optional) is a type of string
          title = toplist_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = toplist_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = toplist_definition.value["title_size"]

          dynamic "custom_link" {
            for_each = toplist_definition.value.custom_link
            content {
              # label - (required) is a type of string
              label = custom_link.value["label"]
              # link - (required) is a type of string
              link = custom_link.value["link"]
            }
          }

          dynamic "request" {
            for_each = toplist_definition.value.request
            content {
              # q - (optional) is a type of string
              q = request.value["q"]

              dynamic "apm_query" {
                for_each = request.value.apm_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = apm_query.value["compute"]
                  # index - (required) is a type of string
                  index = apm_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = apm_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = apm_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = apm_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = apm_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = apm_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "conditional_formats" {
                for_each = request.value.conditional_formats
                content {
                  # comparator - (required) is a type of string
                  comparator = conditional_formats.value["comparator"]
                  # custom_bg_color - (optional) is a type of string
                  custom_bg_color = conditional_formats.value["custom_bg_color"]
                  # custom_fg_color - (optional) is a type of string
                  custom_fg_color = conditional_formats.value["custom_fg_color"]
                  # hide_value - (optional) is a type of bool
                  hide_value = conditional_formats.value["hide_value"]
                  # image_url - (optional) is a type of string
                  image_url = conditional_formats.value["image_url"]
                  # metric - (optional) is a type of string
                  metric = conditional_formats.value["metric"]
                  # palette - (required) is a type of string
                  palette = conditional_formats.value["palette"]
                  # timeframe - (optional) is a type of string
                  timeframe = conditional_formats.value["timeframe"]
                  # value - (required) is a type of number
                  value = conditional_formats.value["value"]
                }
              }

              dynamic "log_query" {
                for_each = request.value.log_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = log_query.value["compute"]
                  # index - (required) is a type of string
                  index = log_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = log_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = log_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = log_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = log_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = log_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "process_query" {
                for_each = request.value.process_query
                content {
                  # filter_by - (optional) is a type of list of string
                  filter_by = process_query.value["filter_by"]
                  # limit - (optional) is a type of number
                  limit = process_query.value["limit"]
                  # metric - (required) is a type of string
                  metric = process_query.value["metric"]
                  # search_by - (optional) is a type of string
                  search_by = process_query.value["search_by"]
                }
              }

              dynamic "rum_query" {
                for_each = request.value.rum_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = rum_query.value["compute"]
                  # index - (required) is a type of string
                  index = rum_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = rum_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = rum_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = rum_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = rum_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = rum_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "security_query" {
                for_each = request.value.security_query
                content {
                  # compute - (optional) is a type of map of string
                  compute = security_query.value["compute"]
                  # index - (required) is a type of string
                  index = security_query.value["index"]
                  # search - (optional) is a type of map of string
                  search = security_query.value["search"]
                  # search_query - (optional) is a type of string
                  search_query = security_query.value["search_query"]

                  dynamic "compute_query" {
                    for_each = security_query.value.compute_query
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = compute_query.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = compute_query.value["facet"]
                      # interval - (optional) is a type of number
                      interval = compute_query.value["interval"]
                    }
                  }

                  dynamic "group_by" {
                    for_each = security_query.value.group_by
                    content {
                      # facet - (optional) is a type of string
                      facet = group_by.value["facet"]
                      # limit - (optional) is a type of number
                      limit = group_by.value["limit"]
                      # sort - (optional) is a type of map of string
                      sort = group_by.value["sort"]

                      dynamic "sort_query" {
                        for_each = group_by.value.sort_query
                        content {
                          # aggregation - (required) is a type of string
                          aggregation = sort_query.value["aggregation"]
                          # facet - (optional) is a type of string
                          facet = sort_query.value["facet"]
                          # order - (required) is a type of string
                          order = sort_query.value["order"]
                        }
                      }

                    }
                  }

                  dynamic "multi_compute" {
                    for_each = security_query.value.multi_compute
                    content {
                      # aggregation - (required) is a type of string
                      aggregation = multi_compute.value["aggregation"]
                      # facet - (optional) is a type of string
                      facet = multi_compute.value["facet"]
                      # interval - (optional) is a type of number
                      interval = multi_compute.value["interval"]
                    }
                  }

                }
              }

              dynamic "style" {
                for_each = request.value.style
                content {
                  # palette - (optional) is a type of string
                  palette = style.value["palette"]
                }
              }

            }
          }

        }
      }

      dynamic "trace_service_definition" {
        for_each = widget.value.trace_service_definition
        content {
          # display_format - (optional) is a type of string
          display_format = trace_service_definition.value["display_format"]
          # env - (required) is a type of string
          env = trace_service_definition.value["env"]
          # live_span - (optional) is a type of string
          live_span = trace_service_definition.value["live_span"]
          # service - (required) is a type of string
          service = trace_service_definition.value["service"]
          # show_breakdown - (optional) is a type of bool
          show_breakdown = trace_service_definition.value["show_breakdown"]
          # show_distribution - (optional) is a type of bool
          show_distribution = trace_service_definition.value["show_distribution"]
          # show_errors - (optional) is a type of bool
          show_errors = trace_service_definition.value["show_errors"]
          # show_hits - (optional) is a type of bool
          show_hits = trace_service_definition.value["show_hits"]
          # show_latency - (optional) is a type of bool
          show_latency = trace_service_definition.value["show_latency"]
          # show_resource_list - (optional) is a type of bool
          show_resource_list = trace_service_definition.value["show_resource_list"]
          # size_format - (optional) is a type of string
          size_format = trace_service_definition.value["size_format"]
          # span_name - (required) is a type of string
          span_name = trace_service_definition.value["span_name"]
          # time - (optional) is a type of map of string
          time = trace_service_definition.value["time"]
          # title - (optional) is a type of string
          title = trace_service_definition.value["title"]
          # title_align - (optional) is a type of string
          title_align = trace_service_definition.value["title_align"]
          # title_size - (optional) is a type of string
          title_size = trace_service_definition.value["title_size"]
        }
      }

      dynamic "widget_layout" {
        for_each = widget.value.widget_layout
        content {
          # height - (required) is a type of number
          height = widget_layout.value["height"]
          # width - (required) is a type of number
          width = widget_layout.value["width"]
          # x - (required) is a type of number
          x = widget_layout.value["x"]
          # y - (required) is a type of number
          y = widget_layout.value["y"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dashboard_lists_removed" {
  description = "returns a set of number"
  value       = datadog_dashboard.this.dashboard_lists_removed
}

output "id" {
  description = "returns a string"
  value       = datadog_dashboard.this.id
}

output "url" {
  description = "returns a string"
  value       = datadog_dashboard.this.url
}

output "this" {
  value = datadog_dashboard.this
}
```

[top](#index)