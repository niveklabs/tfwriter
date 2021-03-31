# fortios_webfilter_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_webfilter_profile" {
  source = "./modules/fortios/r/fortios_webfilter_profile"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # extended_log - (optional) is a type of string
  extended_log = null
  # feature_set - (optional) is a type of string
  feature_set = null
  # https_replacemsg - (optional) is a type of string
  https_replacemsg = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # log_all_url - (optional) is a type of string
  log_all_url = null
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of string
  options = null
  # ovrd_perm - (optional) is a type of string
  ovrd_perm = null
  # post_action - (optional) is a type of string
  post_action = null
  # replacemsg_group - (optional) is a type of string
  replacemsg_group = null
  # web_antiphishing_log - (optional) is a type of string
  web_antiphishing_log = null
  # web_content_log - (optional) is a type of string
  web_content_log = null
  # web_extended_all_action_log - (optional) is a type of string
  web_extended_all_action_log = null
  # web_filter_activex_log - (optional) is a type of string
  web_filter_activex_log = null
  # web_filter_applet_log - (optional) is a type of string
  web_filter_applet_log = null
  # web_filter_command_block_log - (optional) is a type of string
  web_filter_command_block_log = null
  # web_filter_cookie_log - (optional) is a type of string
  web_filter_cookie_log = null
  # web_filter_cookie_removal_log - (optional) is a type of string
  web_filter_cookie_removal_log = null
  # web_filter_js_log - (optional) is a type of string
  web_filter_js_log = null
  # web_filter_jscript_log - (optional) is a type of string
  web_filter_jscript_log = null
  # web_filter_referer_log - (optional) is a type of string
  web_filter_referer_log = null
  # web_filter_unknown_log - (optional) is a type of string
  web_filter_unknown_log = null
  # web_filter_vbs_log - (optional) is a type of string
  web_filter_vbs_log = null
  # web_ftgd_err_log - (optional) is a type of string
  web_ftgd_err_log = null
  # web_ftgd_quota_usage - (optional) is a type of string
  web_ftgd_quota_usage = null
  # web_invalid_domain_log - (optional) is a type of string
  web_invalid_domain_log = null
  # web_url_log - (optional) is a type of string
  web_url_log = null
  # wisp - (optional) is a type of string
  wisp = null
  # wisp_algorithm - (optional) is a type of string
  wisp_algorithm = null
  # youtube_channel_status - (optional) is a type of string
  youtube_channel_status = null

  antiphish = [{
    check_basic_auth = null
    check_uri        = null
    custom_patterns = [{
      category = null
      pattern  = null
    }]
    default_action    = null
    domain_controller = null
    inspection_entries = [{
      action              = null
      fortiguard_category = null
      name                = null
    }]
    max_body_len = null
    status       = null
  }]

  file_filter = [{
    entries = [{
      action    = null
      comment   = null
      direction = null
      file_type = [{
        name = null
      }]
      filter             = null
      password_protected = null
      protocol           = null
    }]
    log                   = null
    scan_archive_contents = null
    status                = null
  }]

  ftgd_wf = [{
    exempt_quota = null
    filters = [{
      action = null
      auth_usr_grp = [{
        name = null
      }]
      category              = null
      id                    = null
      log                   = null
      override_replacemsg   = null
      warn_duration         = null
      warning_duration_type = null
      warning_prompt        = null
    }]
    max_quota_timeout = null
    options           = null
    ovrd              = null
    quota = [{
      category            = null
      duration            = null
      id                  = null
      override_replacemsg = null
      type                = null
      unit                = null
      value               = null
    }]
    rate_crl_urls        = null
    rate_css_urls        = null
    rate_image_urls      = null
    rate_javascript_urls = null
  }]

  override = [{
    ovrd_cookie   = null
    ovrd_dur      = null
    ovrd_dur_mode = null
    ovrd_scope    = null
    ovrd_user_group = [{
      name = null
    }]
    profile = [{
      name = null
    }]
    profile_attribute = null
    profile_type      = null
  }]

  web = [{
    allowlist           = null
    blacklist           = null
    blocklist           = null
    bword_table         = null
    bword_threshold     = null
    content_header_list = null
    keyword_match = [{
      pattern = null
    }]
    log_search       = null
    safe_search      = null
    urlfilter_table  = null
    whitelist        = null
    youtube_restrict = null
  }]

  wisp_servers = [{
    name = null
  }]

  youtube_channel_filter = [{
    channel_id = null
    comment    = null
    id         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "feature_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_replacemsg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_all_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ovrd_perm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "post_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacemsg_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_antiphishing_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_content_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_extended_all_action_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_activex_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_applet_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_command_block_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_cookie_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_cookie_removal_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_js_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_jscript_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_referer_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_unknown_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_filter_vbs_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_ftgd_err_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_ftgd_quota_usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_invalid_domain_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_url_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wisp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wisp_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "youtube_channel_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "antiphish" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      check_basic_auth = string
      check_uri        = string
      custom_patterns = list(object(
        {
          category = string
          pattern  = string
        }
      ))
      default_action    = string
      domain_controller = string
      inspection_entries = list(object(
        {
          action              = string
          fortiguard_category = string
          name                = string
        }
      ))
      max_body_len = number
      status       = string
    }
  ))
  default = []
}

variable "file_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      entries = list(object(
        {
          action    = string
          comment   = string
          direction = string
          file_type = list(object(
            {
              name = string
            }
          ))
          filter             = string
          password_protected = string
          protocol           = string
        }
      ))
      log                   = string
      scan_archive_contents = string
      status                = string
    }
  ))
  default = []
}

variable "ftgd_wf" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      exempt_quota = string
      filters = list(object(
        {
          action = string
          auth_usr_grp = list(object(
            {
              name = string
            }
          ))
          category              = number
          id                    = number
          log                   = string
          override_replacemsg   = string
          warn_duration         = string
          warning_duration_type = string
          warning_prompt        = string
        }
      ))
      max_quota_timeout = number
      options           = string
      ovrd              = string
      quota = list(object(
        {
          category            = string
          duration            = string
          id                  = number
          override_replacemsg = string
          type                = string
          unit                = string
          value               = number
        }
      ))
      rate_crl_urls        = string
      rate_css_urls        = string
      rate_image_urls      = string
      rate_javascript_urls = string
    }
  ))
  default = []
}

variable "override" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ovrd_cookie   = string
      ovrd_dur      = string
      ovrd_dur_mode = string
      ovrd_scope    = string
      ovrd_user_group = list(object(
        {
          name = string
        }
      ))
      profile = list(object(
        {
          name = string
        }
      ))
      profile_attribute = string
      profile_type      = string
    }
  ))
  default = []
}

variable "web" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowlist           = string
      blacklist           = string
      blocklist           = string
      bword_table         = number
      bword_threshold     = number
      content_header_list = number
      keyword_match = list(object(
        {
          pattern = string
        }
      ))
      log_search       = string
      safe_search      = string
      urlfilter_table  = number
      whitelist        = string
      youtube_restrict = string
    }
  ))
  default = []
}

variable "wisp_servers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "youtube_channel_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      channel_id = string
      comment    = string
      id         = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_profile" "this" {
  comment                       = var.comment
  dynamic_sort_subtable         = var.dynamic_sort_subtable
  extended_log                  = var.extended_log
  feature_set                   = var.feature_set
  https_replacemsg              = var.https_replacemsg
  inspection_mode               = var.inspection_mode
  log_all_url                   = var.log_all_url
  name                          = var.name
  options                       = var.options
  ovrd_perm                     = var.ovrd_perm
  post_action                   = var.post_action
  replacemsg_group              = var.replacemsg_group
  web_antiphishing_log          = var.web_antiphishing_log
  web_content_log               = var.web_content_log
  web_extended_all_action_log   = var.web_extended_all_action_log
  web_filter_activex_log        = var.web_filter_activex_log
  web_filter_applet_log         = var.web_filter_applet_log
  web_filter_command_block_log  = var.web_filter_command_block_log
  web_filter_cookie_log         = var.web_filter_cookie_log
  web_filter_cookie_removal_log = var.web_filter_cookie_removal_log
  web_filter_js_log             = var.web_filter_js_log
  web_filter_jscript_log        = var.web_filter_jscript_log
  web_filter_referer_log        = var.web_filter_referer_log
  web_filter_unknown_log        = var.web_filter_unknown_log
  web_filter_vbs_log            = var.web_filter_vbs_log
  web_ftgd_err_log              = var.web_ftgd_err_log
  web_ftgd_quota_usage          = var.web_ftgd_quota_usage
  web_invalid_domain_log        = var.web_invalid_domain_log
  web_url_log                   = var.web_url_log
  wisp                          = var.wisp
  wisp_algorithm                = var.wisp_algorithm
  youtube_channel_status        = var.youtube_channel_status

  dynamic "antiphish" {
    for_each = var.antiphish
    content {
      check_basic_auth  = antiphish.value["check_basic_auth"]
      check_uri         = antiphish.value["check_uri"]
      default_action    = antiphish.value["default_action"]
      domain_controller = antiphish.value["domain_controller"]
      max_body_len      = antiphish.value["max_body_len"]
      status            = antiphish.value["status"]

      dynamic "custom_patterns" {
        for_each = antiphish.value.custom_patterns
        content {
          category = custom_patterns.value["category"]
          pattern  = custom_patterns.value["pattern"]
        }
      }

      dynamic "inspection_entries" {
        for_each = antiphish.value.inspection_entries
        content {
          action              = inspection_entries.value["action"]
          fortiguard_category = inspection_entries.value["fortiguard_category"]
          name                = inspection_entries.value["name"]
        }
      }

    }
  }

  dynamic "file_filter" {
    for_each = var.file_filter
    content {
      log                   = file_filter.value["log"]
      scan_archive_contents = file_filter.value["scan_archive_contents"]
      status                = file_filter.value["status"]

      dynamic "entries" {
        for_each = file_filter.value.entries
        content {
          action             = entries.value["action"]
          comment            = entries.value["comment"]
          direction          = entries.value["direction"]
          filter             = entries.value["filter"]
          password_protected = entries.value["password_protected"]
          protocol           = entries.value["protocol"]

          dynamic "file_type" {
            for_each = entries.value.file_type
            content {
              name = file_type.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "ftgd_wf" {
    for_each = var.ftgd_wf
    content {
      exempt_quota         = ftgd_wf.value["exempt_quota"]
      max_quota_timeout    = ftgd_wf.value["max_quota_timeout"]
      options              = ftgd_wf.value["options"]
      ovrd                 = ftgd_wf.value["ovrd"]
      rate_crl_urls        = ftgd_wf.value["rate_crl_urls"]
      rate_css_urls        = ftgd_wf.value["rate_css_urls"]
      rate_image_urls      = ftgd_wf.value["rate_image_urls"]
      rate_javascript_urls = ftgd_wf.value["rate_javascript_urls"]

      dynamic "filters" {
        for_each = ftgd_wf.value.filters
        content {
          action                = filters.value["action"]
          category              = filters.value["category"]
          id                    = filters.value["id"]
          log                   = filters.value["log"]
          override_replacemsg   = filters.value["override_replacemsg"]
          warn_duration         = filters.value["warn_duration"]
          warning_duration_type = filters.value["warning_duration_type"]
          warning_prompt        = filters.value["warning_prompt"]

          dynamic "auth_usr_grp" {
            for_each = filters.value.auth_usr_grp
            content {
              name = auth_usr_grp.value["name"]
            }
          }

        }
      }

      dynamic "quota" {
        for_each = ftgd_wf.value.quota
        content {
          category            = quota.value["category"]
          duration            = quota.value["duration"]
          id                  = quota.value["id"]
          override_replacemsg = quota.value["override_replacemsg"]
          type                = quota.value["type"]
          unit                = quota.value["unit"]
          value               = quota.value["value"]
        }
      }

    }
  }

  dynamic "override" {
    for_each = var.override
    content {
      ovrd_cookie       = override.value["ovrd_cookie"]
      ovrd_dur          = override.value["ovrd_dur"]
      ovrd_dur_mode     = override.value["ovrd_dur_mode"]
      ovrd_scope        = override.value["ovrd_scope"]
      profile_attribute = override.value["profile_attribute"]
      profile_type      = override.value["profile_type"]

      dynamic "ovrd_user_group" {
        for_each = override.value.ovrd_user_group
        content {
          name = ovrd_user_group.value["name"]
        }
      }

      dynamic "profile" {
        for_each = override.value.profile
        content {
          name = profile.value["name"]
        }
      }

    }
  }

  dynamic "web" {
    for_each = var.web
    content {
      allowlist           = web.value["allowlist"]
      blacklist           = web.value["blacklist"]
      blocklist           = web.value["blocklist"]
      bword_table         = web.value["bword_table"]
      bword_threshold     = web.value["bword_threshold"]
      content_header_list = web.value["content_header_list"]
      log_search          = web.value["log_search"]
      safe_search         = web.value["safe_search"]
      urlfilter_table     = web.value["urlfilter_table"]
      whitelist           = web.value["whitelist"]
      youtube_restrict    = web.value["youtube_restrict"]

      dynamic "keyword_match" {
        for_each = web.value.keyword_match
        content {
          pattern = keyword_match.value["pattern"]
        }
      }

    }
  }

  dynamic "wisp_servers" {
    for_each = var.wisp_servers
    content {
      name = wisp_servers.value["name"]
    }
  }

  dynamic "youtube_channel_filter" {
    for_each = var.youtube_channel_filter
    content {
      channel_id = youtube_channel_filter.value["channel_id"]
      comment    = youtube_channel_filter.value["comment"]
      id         = youtube_channel_filter.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "extended_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.extended_log
}

output "feature_set" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.feature_set
}

output "https_replacemsg" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.https_replacemsg
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.id
}

output "inspection_mode" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.inspection_mode
}

output "log_all_url" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.log_all_url
}

output "options" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.options
}

output "ovrd_perm" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.ovrd_perm
}

output "post_action" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.post_action
}

output "replacemsg_group" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.replacemsg_group
}

output "web_antiphishing_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_antiphishing_log
}

output "web_content_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_content_log
}

output "web_extended_all_action_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_extended_all_action_log
}

output "web_filter_activex_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_activex_log
}

output "web_filter_applet_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_applet_log
}

output "web_filter_command_block_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_command_block_log
}

output "web_filter_cookie_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_cookie_log
}

output "web_filter_cookie_removal_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_cookie_removal_log
}

output "web_filter_js_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_js_log
}

output "web_filter_jscript_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_jscript_log
}

output "web_filter_referer_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_referer_log
}

output "web_filter_unknown_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_unknown_log
}

output "web_filter_vbs_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_filter_vbs_log
}

output "web_ftgd_err_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_ftgd_err_log
}

output "web_ftgd_quota_usage" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_ftgd_quota_usage
}

output "web_invalid_domain_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_invalid_domain_log
}

output "web_url_log" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.web_url_log
}

output "wisp" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.wisp
}

output "wisp_algorithm" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.wisp_algorithm
}

output "youtube_channel_status" {
  description = "returns a string"
  value       = fortios_webfilter_profile.this.youtube_channel_status
}

output "this" {
  value = fortios_webfilter_profile.this
}
```

[top](#index)