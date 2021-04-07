# oci_waas_waas_policy

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_waas_waas_policy" {
  source = "./modules/oci/r/oci_waas_waas_policy"

  # additional_domains - (optional) is a type of list of string
  additional_domains = []
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (required) is a type of string
  domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

  origin_groups = [{
    label = null
    origin_group = [{
      origin = null
      weight = null
    }]
  }]

  origins = [{
    custom_headers = [{
      name  = null
      value = null
    }]
    http_port  = null
    https_port = null
    label      = null
    uri        = null
  }]

  policy_config = [{
    certificate_id        = null
    cipher_group          = null
    client_address_header = null
    health_checks = [{
      expected_response_code_group   = []
      expected_response_text         = null
      headers                        = {}
      healthy_threshold              = null
      interval_in_seconds            = null
      is_enabled                     = null
      is_response_text_check_enabled = null
      method                         = null
      path                           = null
      timeout_in_seconds             = null
      unhealthy_threshold            = null
    }]
    is_behind_cdn                 = null
    is_cache_control_respected    = null
    is_https_enabled              = null
    is_https_forced               = null
    is_origin_compression_enabled = null
    is_response_buffering_enabled = null
    is_sni_enabled                = null
    load_balancing_method = [{
      domain                     = null
      expiration_time_in_seconds = null
      method                     = null
      name                       = null
    }]
    tls_protocols           = []
    websocket_path_prefixes = []
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  waf_config = [{
    access_rules = [{
      action                       = null
      block_action                 = null
      block_error_page_code        = null
      block_error_page_description = null
      block_error_page_message     = null
      block_response_code          = null
      bypass_challenges            = []
      captcha_footer               = null
      captcha_header               = null
      captcha_submit_label         = null
      captcha_title                = null
      criteria = [{
        condition         = null
        is_case_sensitive = null
        value             = null
      }]
      name                   = null
      redirect_response_code = null
      redirect_url           = null
      response_header_manipulation = [{
        action = null
        header = null
        value  = null
      }]
    }]
    address_rate_limiting = [{
      allowed_rate_per_address      = null
      block_response_code           = null
      is_enabled                    = null
      max_delayed_count_per_address = null
    }]
    caching_rules = [{
      action                  = null
      caching_duration        = null
      client_caching_duration = null
      criteria = [{
        condition = null
        value     = null
      }]
      is_client_caching_enabled = null
      key                       = null
      name                      = null
    }]
    captchas = [{
      failure_message               = null
      footer_text                   = null
      header_text                   = null
      session_expiration_in_seconds = null
      submit_label                  = null
      title                         = null
      url                           = null
    }]
    custom_protection_rules = [{
      action = null
      exclusions = [{
        exclusions = []
        target     = null
      }]
      id = null
    }]
    device_fingerprint_challenge = [{
      action                       = null
      action_expiration_in_seconds = null
      challenge_settings = [{
        block_action                 = null
        block_error_page_code        = null
        block_error_page_description = null
        block_error_page_message     = null
        block_response_code          = null
        captcha_footer               = null
        captcha_header               = null
        captcha_submit_label         = null
        captcha_title                = null
      }]
      failure_threshold                       = null
      failure_threshold_expiration_in_seconds = null
      is_enabled                              = null
      max_address_count                       = null
      max_address_count_expiration_in_seconds = null
    }]
    human_interaction_challenge = [{
      action                       = null
      action_expiration_in_seconds = null
      challenge_settings = [{
        block_action                 = null
        block_error_page_code        = null
        block_error_page_description = null
        block_error_page_message     = null
        block_response_code          = null
        captcha_footer               = null
        captcha_header               = null
        captcha_submit_label         = null
        captcha_title                = null
      }]
      failure_threshold                       = null
      failure_threshold_expiration_in_seconds = null
      interaction_threshold                   = null
      is_enabled                              = null
      is_nat_enabled                          = null
      recording_period_in_seconds             = null
      set_http_header = [{
        name  = null
        value = null
      }]
    }]
    js_challenge = [{
      action                       = null
      action_expiration_in_seconds = null
      are_redirects_challenged     = null
      challenge_settings = [{
        block_action                 = null
        block_error_page_code        = null
        block_error_page_description = null
        block_error_page_message     = null
        block_response_code          = null
        captcha_footer               = null
        captcha_header               = null
        captcha_submit_label         = null
        captcha_title                = null
      }]
      criteria = [{
        condition         = null
        is_case_sensitive = null
        value             = null
      }]
      failure_threshold = null
      is_enabled        = null
      is_nat_enabled    = null
      set_http_header = [{
        name  = null
        value = null
      }]
    }]
    origin        = null
    origin_groups = []
    protection_settings = [{
      allowed_http_methods               = []
      block_action                       = null
      block_error_page_code              = null
      block_error_page_description       = null
      block_error_page_message           = null
      block_response_code                = null
      is_response_inspected              = null
      max_argument_count                 = null
      max_name_length_per_argument       = null
      max_response_size_in_ki_b          = null
      max_total_name_length_of_arguments = null
      media_types                        = []
      recommendations_period_in_days     = null
    }]
    whitelists = [{
      address_lists = []
      addresses     = []
      name          = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_domains" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "origin_groups" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      label = string
      origin_group = list(object(
        {
          origin = string
          weight = number
        }
      ))
    }
  ))
  default = []
}

variable "origins" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      custom_headers = list(object(
        {
          name  = string
          value = string
        }
      ))
      http_port  = number
      https_port = number
      label      = string
      uri        = string
    }
  ))
  default = []
}

variable "policy_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_id        = string
      cipher_group          = string
      client_address_header = string
      health_checks = list(object(
        {
          expected_response_code_group   = list(string)
          expected_response_text         = string
          headers                        = map(string)
          healthy_threshold              = number
          interval_in_seconds            = number
          is_enabled                     = bool
          is_response_text_check_enabled = bool
          method                         = string
          path                           = string
          timeout_in_seconds             = number
          unhealthy_threshold            = number
        }
      ))
      is_behind_cdn                 = bool
      is_cache_control_respected    = bool
      is_https_enabled              = bool
      is_https_forced               = bool
      is_origin_compression_enabled = bool
      is_response_buffering_enabled = bool
      is_sni_enabled                = bool
      load_balancing_method = list(object(
        {
          domain                     = string
          expiration_time_in_seconds = number
          method                     = string
          name                       = string
        }
      ))
      tls_protocols           = list(string)
      websocket_path_prefixes = list(string)
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

variable "waf_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_rules = list(object(
        {
          action                       = string
          block_action                 = string
          block_error_page_code        = string
          block_error_page_description = string
          block_error_page_message     = string
          block_response_code          = number
          bypass_challenges            = list(string)
          captcha_footer               = string
          captcha_header               = string
          captcha_submit_label         = string
          captcha_title                = string
          criteria = list(object(
            {
              condition         = string
              is_case_sensitive = bool
              value             = string
            }
          ))
          name                   = string
          redirect_response_code = string
          redirect_url           = string
          response_header_manipulation = list(object(
            {
              action = string
              header = string
              value  = string
            }
          ))
        }
      ))
      address_rate_limiting = list(object(
        {
          allowed_rate_per_address      = number
          block_response_code           = number
          is_enabled                    = bool
          max_delayed_count_per_address = number
        }
      ))
      caching_rules = list(object(
        {
          action                  = string
          caching_duration        = string
          client_caching_duration = string
          criteria = list(object(
            {
              condition = string
              value     = string
            }
          ))
          is_client_caching_enabled = bool
          key                       = string
          name                      = string
        }
      ))
      captchas = list(object(
        {
          failure_message               = string
          footer_text                   = string
          header_text                   = string
          session_expiration_in_seconds = number
          submit_label                  = string
          title                         = string
          url                           = string
        }
      ))
      custom_protection_rules = list(object(
        {
          action = string
          exclusions = list(object(
            {
              exclusions = list(string)
              target     = string
            }
          ))
          id = string
        }
      ))
      device_fingerprint_challenge = list(object(
        {
          action                       = string
          action_expiration_in_seconds = number
          challenge_settings = list(object(
            {
              block_action                 = string
              block_error_page_code        = string
              block_error_page_description = string
              block_error_page_message     = string
              block_response_code          = number
              captcha_footer               = string
              captcha_header               = string
              captcha_submit_label         = string
              captcha_title                = string
            }
          ))
          failure_threshold                       = number
          failure_threshold_expiration_in_seconds = number
          is_enabled                              = bool
          max_address_count                       = number
          max_address_count_expiration_in_seconds = number
        }
      ))
      human_interaction_challenge = list(object(
        {
          action                       = string
          action_expiration_in_seconds = number
          challenge_settings = list(object(
            {
              block_action                 = string
              block_error_page_code        = string
              block_error_page_description = string
              block_error_page_message     = string
              block_response_code          = number
              captcha_footer               = string
              captcha_header               = string
              captcha_submit_label         = string
              captcha_title                = string
            }
          ))
          failure_threshold                       = number
          failure_threshold_expiration_in_seconds = number
          interaction_threshold                   = number
          is_enabled                              = bool
          is_nat_enabled                          = bool
          recording_period_in_seconds             = number
          set_http_header = list(object(
            {
              name  = string
              value = string
            }
          ))
        }
      ))
      js_challenge = list(object(
        {
          action                       = string
          action_expiration_in_seconds = number
          are_redirects_challenged     = bool
          challenge_settings = list(object(
            {
              block_action                 = string
              block_error_page_code        = string
              block_error_page_description = string
              block_error_page_message     = string
              block_response_code          = number
              captcha_footer               = string
              captcha_header               = string
              captcha_submit_label         = string
              captcha_title                = string
            }
          ))
          criteria = list(object(
            {
              condition         = string
              is_case_sensitive = bool
              value             = string
            }
          ))
          failure_threshold = number
          is_enabled        = bool
          is_nat_enabled    = bool
          set_http_header = list(object(
            {
              name  = string
              value = string
            }
          ))
        }
      ))
      origin        = string
      origin_groups = list(string)
      protection_settings = list(object(
        {
          allowed_http_methods               = list(string)
          block_action                       = string
          block_error_page_code              = string
          block_error_page_description       = string
          block_error_page_message           = string
          block_response_code                = number
          is_response_inspected              = bool
          max_argument_count                 = number
          max_name_length_per_argument       = number
          max_response_size_in_ki_b          = number
          max_total_name_length_of_arguments = number
          media_types                        = list(string)
          recommendations_period_in_days     = number
        }
      ))
      whitelists = list(object(
        {
          address_lists = list(string)
          addresses     = list(string)
          name          = string
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
resource "oci_waas_waas_policy" "this" {
  # additional_domains - (optional) is a type of list of string
  additional_domains = var.additional_domains
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # domain - (required) is a type of string
  domain = var.domain
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags

  dynamic "origin_groups" {
    for_each = var.origin_groups
    content {
      # label - (required) is a type of string
      label = origin_groups.value["label"]

      dynamic "origin_group" {
        for_each = origin_groups.value.origin_group
        content {
          # origin - (required) is a type of string
          origin = origin_group.value["origin"]
          # weight - (optional) is a type of number
          weight = origin_group.value["weight"]
        }
      }

    }
  }

  dynamic "origins" {
    for_each = var.origins
    content {
      # http_port - (optional) is a type of number
      http_port = origins.value["http_port"]
      # https_port - (optional) is a type of number
      https_port = origins.value["https_port"]
      # label - (required) is a type of string
      label = origins.value["label"]
      # uri - (required) is a type of string
      uri = origins.value["uri"]

      dynamic "custom_headers" {
        for_each = origins.value.custom_headers
        content {
          # name - (required) is a type of string
          name = custom_headers.value["name"]
          # value - (required) is a type of string
          value = custom_headers.value["value"]
        }
      }

    }
  }

  dynamic "policy_config" {
    for_each = var.policy_config
    content {
      # certificate_id - (optional) is a type of string
      certificate_id = policy_config.value["certificate_id"]
      # cipher_group - (optional) is a type of string
      cipher_group = policy_config.value["cipher_group"]
      # client_address_header - (optional) is a type of string
      client_address_header = policy_config.value["client_address_header"]
      # is_behind_cdn - (optional) is a type of bool
      is_behind_cdn = policy_config.value["is_behind_cdn"]
      # is_cache_control_respected - (optional) is a type of bool
      is_cache_control_respected = policy_config.value["is_cache_control_respected"]
      # is_https_enabled - (optional) is a type of bool
      is_https_enabled = policy_config.value["is_https_enabled"]
      # is_https_forced - (optional) is a type of bool
      is_https_forced = policy_config.value["is_https_forced"]
      # is_origin_compression_enabled - (optional) is a type of bool
      is_origin_compression_enabled = policy_config.value["is_origin_compression_enabled"]
      # is_response_buffering_enabled - (optional) is a type of bool
      is_response_buffering_enabled = policy_config.value["is_response_buffering_enabled"]
      # is_sni_enabled - (optional) is a type of bool
      is_sni_enabled = policy_config.value["is_sni_enabled"]
      # tls_protocols - (optional) is a type of list of string
      tls_protocols = policy_config.value["tls_protocols"]
      # websocket_path_prefixes - (optional) is a type of list of string
      websocket_path_prefixes = policy_config.value["websocket_path_prefixes"]

      dynamic "health_checks" {
        for_each = policy_config.value.health_checks
        content {
          # expected_response_code_group - (optional) is a type of list of string
          expected_response_code_group = health_checks.value["expected_response_code_group"]
          # expected_response_text - (optional) is a type of string
          expected_response_text = health_checks.value["expected_response_text"]
          # headers - (optional) is a type of map of string
          headers = health_checks.value["headers"]
          # healthy_threshold - (optional) is a type of number
          healthy_threshold = health_checks.value["healthy_threshold"]
          # interval_in_seconds - (optional) is a type of number
          interval_in_seconds = health_checks.value["interval_in_seconds"]
          # is_enabled - (optional) is a type of bool
          is_enabled = health_checks.value["is_enabled"]
          # is_response_text_check_enabled - (optional) is a type of bool
          is_response_text_check_enabled = health_checks.value["is_response_text_check_enabled"]
          # method - (optional) is a type of string
          method = health_checks.value["method"]
          # path - (optional) is a type of string
          path = health_checks.value["path"]
          # timeout_in_seconds - (optional) is a type of number
          timeout_in_seconds = health_checks.value["timeout_in_seconds"]
          # unhealthy_threshold - (optional) is a type of number
          unhealthy_threshold = health_checks.value["unhealthy_threshold"]
        }
      }

      dynamic "load_balancing_method" {
        for_each = policy_config.value.load_balancing_method
        content {
          # domain - (optional) is a type of string
          domain = load_balancing_method.value["domain"]
          # expiration_time_in_seconds - (optional) is a type of number
          expiration_time_in_seconds = load_balancing_method.value["expiration_time_in_seconds"]
          # method - (required) is a type of string
          method = load_balancing_method.value["method"]
          # name - (optional) is a type of string
          name = load_balancing_method.value["name"]
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

  dynamic "waf_config" {
    for_each = var.waf_config
    content {
      # origin - (optional) is a type of string
      origin = waf_config.value["origin"]
      # origin_groups - (optional) is a type of list of string
      origin_groups = waf_config.value["origin_groups"]

      dynamic "access_rules" {
        for_each = waf_config.value.access_rules
        content {
          # action - (required) is a type of string
          action = access_rules.value["action"]
          # block_action - (optional) is a type of string
          block_action = access_rules.value["block_action"]
          # block_error_page_code - (optional) is a type of string
          block_error_page_code = access_rules.value["block_error_page_code"]
          # block_error_page_description - (optional) is a type of string
          block_error_page_description = access_rules.value["block_error_page_description"]
          # block_error_page_message - (optional) is a type of string
          block_error_page_message = access_rules.value["block_error_page_message"]
          # block_response_code - (optional) is a type of number
          block_response_code = access_rules.value["block_response_code"]
          # bypass_challenges - (optional) is a type of list of string
          bypass_challenges = access_rules.value["bypass_challenges"]
          # captcha_footer - (optional) is a type of string
          captcha_footer = access_rules.value["captcha_footer"]
          # captcha_header - (optional) is a type of string
          captcha_header = access_rules.value["captcha_header"]
          # captcha_submit_label - (optional) is a type of string
          captcha_submit_label = access_rules.value["captcha_submit_label"]
          # captcha_title - (optional) is a type of string
          captcha_title = access_rules.value["captcha_title"]
          # name - (required) is a type of string
          name = access_rules.value["name"]
          # redirect_response_code - (optional) is a type of string
          redirect_response_code = access_rules.value["redirect_response_code"]
          # redirect_url - (optional) is a type of string
          redirect_url = access_rules.value["redirect_url"]

          dynamic "criteria" {
            for_each = access_rules.value.criteria
            content {
              # condition - (required) is a type of string
              condition = criteria.value["condition"]
              # is_case_sensitive - (optional) is a type of bool
              is_case_sensitive = criteria.value["is_case_sensitive"]
              # value - (required) is a type of string
              value = criteria.value["value"]
            }
          }

          dynamic "response_header_manipulation" {
            for_each = access_rules.value.response_header_manipulation
            content {
              # action - (required) is a type of string
              action = response_header_manipulation.value["action"]
              # header - (required) is a type of string
              header = response_header_manipulation.value["header"]
              # value - (optional) is a type of string
              value = response_header_manipulation.value["value"]
            }
          }

        }
      }

      dynamic "address_rate_limiting" {
        for_each = waf_config.value.address_rate_limiting
        content {
          # allowed_rate_per_address - (optional) is a type of number
          allowed_rate_per_address = address_rate_limiting.value["allowed_rate_per_address"]
          # block_response_code - (optional) is a type of number
          block_response_code = address_rate_limiting.value["block_response_code"]
          # is_enabled - (required) is a type of bool
          is_enabled = address_rate_limiting.value["is_enabled"]
          # max_delayed_count_per_address - (optional) is a type of number
          max_delayed_count_per_address = address_rate_limiting.value["max_delayed_count_per_address"]
        }
      }

      dynamic "caching_rules" {
        for_each = waf_config.value.caching_rules
        content {
          # action - (required) is a type of string
          action = caching_rules.value["action"]
          # caching_duration - (optional) is a type of string
          caching_duration = caching_rules.value["caching_duration"]
          # client_caching_duration - (optional) is a type of string
          client_caching_duration = caching_rules.value["client_caching_duration"]
          # is_client_caching_enabled - (optional) is a type of bool
          is_client_caching_enabled = caching_rules.value["is_client_caching_enabled"]
          # key - (optional) is a type of string
          key = caching_rules.value["key"]
          # name - (required) is a type of string
          name = caching_rules.value["name"]

          dynamic "criteria" {
            for_each = caching_rules.value.criteria
            content {
              # condition - (required) is a type of string
              condition = criteria.value["condition"]
              # value - (required) is a type of string
              value = criteria.value["value"]
            }
          }

        }
      }

      dynamic "captchas" {
        for_each = waf_config.value.captchas
        content {
          # failure_message - (required) is a type of string
          failure_message = captchas.value["failure_message"]
          # footer_text - (optional) is a type of string
          footer_text = captchas.value["footer_text"]
          # header_text - (optional) is a type of string
          header_text = captchas.value["header_text"]
          # session_expiration_in_seconds - (required) is a type of number
          session_expiration_in_seconds = captchas.value["session_expiration_in_seconds"]
          # submit_label - (required) is a type of string
          submit_label = captchas.value["submit_label"]
          # title - (required) is a type of string
          title = captchas.value["title"]
          # url - (required) is a type of string
          url = captchas.value["url"]
        }
      }

      dynamic "custom_protection_rules" {
        for_each = waf_config.value.custom_protection_rules
        content {
          # action - (optional) is a type of string
          action = custom_protection_rules.value["action"]
          # id - (optional) is a type of string
          id = custom_protection_rules.value["id"]

          dynamic "exclusions" {
            for_each = custom_protection_rules.value.exclusions
            content {
              # exclusions - (optional) is a type of list of string
              exclusions = exclusions.value["exclusions"]
              # target - (optional) is a type of string
              target = exclusions.value["target"]
            }
          }

        }
      }

      dynamic "device_fingerprint_challenge" {
        for_each = waf_config.value.device_fingerprint_challenge
        content {
          # action - (optional) is a type of string
          action = device_fingerprint_challenge.value["action"]
          # action_expiration_in_seconds - (optional) is a type of number
          action_expiration_in_seconds = device_fingerprint_challenge.value["action_expiration_in_seconds"]
          # failure_threshold - (optional) is a type of number
          failure_threshold = device_fingerprint_challenge.value["failure_threshold"]
          # failure_threshold_expiration_in_seconds - (optional) is a type of number
          failure_threshold_expiration_in_seconds = device_fingerprint_challenge.value["failure_threshold_expiration_in_seconds"]
          # is_enabled - (required) is a type of bool
          is_enabled = device_fingerprint_challenge.value["is_enabled"]
          # max_address_count - (optional) is a type of number
          max_address_count = device_fingerprint_challenge.value["max_address_count"]
          # max_address_count_expiration_in_seconds - (optional) is a type of number
          max_address_count_expiration_in_seconds = device_fingerprint_challenge.value["max_address_count_expiration_in_seconds"]

          dynamic "challenge_settings" {
            for_each = device_fingerprint_challenge.value.challenge_settings
            content {
              # block_action - (optional) is a type of string
              block_action = challenge_settings.value["block_action"]
              # block_error_page_code - (optional) is a type of string
              block_error_page_code = challenge_settings.value["block_error_page_code"]
              # block_error_page_description - (optional) is a type of string
              block_error_page_description = challenge_settings.value["block_error_page_description"]
              # block_error_page_message - (optional) is a type of string
              block_error_page_message = challenge_settings.value["block_error_page_message"]
              # block_response_code - (optional) is a type of number
              block_response_code = challenge_settings.value["block_response_code"]
              # captcha_footer - (optional) is a type of string
              captcha_footer = challenge_settings.value["captcha_footer"]
              # captcha_header - (optional) is a type of string
              captcha_header = challenge_settings.value["captcha_header"]
              # captcha_submit_label - (optional) is a type of string
              captcha_submit_label = challenge_settings.value["captcha_submit_label"]
              # captcha_title - (optional) is a type of string
              captcha_title = challenge_settings.value["captcha_title"]
            }
          }

        }
      }

      dynamic "human_interaction_challenge" {
        for_each = waf_config.value.human_interaction_challenge
        content {
          # action - (optional) is a type of string
          action = human_interaction_challenge.value["action"]
          # action_expiration_in_seconds - (optional) is a type of number
          action_expiration_in_seconds = human_interaction_challenge.value["action_expiration_in_seconds"]
          # failure_threshold - (optional) is a type of number
          failure_threshold = human_interaction_challenge.value["failure_threshold"]
          # failure_threshold_expiration_in_seconds - (optional) is a type of number
          failure_threshold_expiration_in_seconds = human_interaction_challenge.value["failure_threshold_expiration_in_seconds"]
          # interaction_threshold - (optional) is a type of number
          interaction_threshold = human_interaction_challenge.value["interaction_threshold"]
          # is_enabled - (required) is a type of bool
          is_enabled = human_interaction_challenge.value["is_enabled"]
          # is_nat_enabled - (optional) is a type of bool
          is_nat_enabled = human_interaction_challenge.value["is_nat_enabled"]
          # recording_period_in_seconds - (optional) is a type of number
          recording_period_in_seconds = human_interaction_challenge.value["recording_period_in_seconds"]

          dynamic "challenge_settings" {
            for_each = human_interaction_challenge.value.challenge_settings
            content {
              # block_action - (optional) is a type of string
              block_action = challenge_settings.value["block_action"]
              # block_error_page_code - (optional) is a type of string
              block_error_page_code = challenge_settings.value["block_error_page_code"]
              # block_error_page_description - (optional) is a type of string
              block_error_page_description = challenge_settings.value["block_error_page_description"]
              # block_error_page_message - (optional) is a type of string
              block_error_page_message = challenge_settings.value["block_error_page_message"]
              # block_response_code - (optional) is a type of number
              block_response_code = challenge_settings.value["block_response_code"]
              # captcha_footer - (optional) is a type of string
              captcha_footer = challenge_settings.value["captcha_footer"]
              # captcha_header - (optional) is a type of string
              captcha_header = challenge_settings.value["captcha_header"]
              # captcha_submit_label - (optional) is a type of string
              captcha_submit_label = challenge_settings.value["captcha_submit_label"]
              # captcha_title - (optional) is a type of string
              captcha_title = challenge_settings.value["captcha_title"]
            }
          }

          dynamic "set_http_header" {
            for_each = human_interaction_challenge.value.set_http_header
            content {
              # name - (required) is a type of string
              name = set_http_header.value["name"]
              # value - (required) is a type of string
              value = set_http_header.value["value"]
            }
          }

        }
      }

      dynamic "js_challenge" {
        for_each = waf_config.value.js_challenge
        content {
          # action - (optional) is a type of string
          action = js_challenge.value["action"]
          # action_expiration_in_seconds - (optional) is a type of number
          action_expiration_in_seconds = js_challenge.value["action_expiration_in_seconds"]
          # are_redirects_challenged - (optional) is a type of bool
          are_redirects_challenged = js_challenge.value["are_redirects_challenged"]
          # failure_threshold - (optional) is a type of number
          failure_threshold = js_challenge.value["failure_threshold"]
          # is_enabled - (required) is a type of bool
          is_enabled = js_challenge.value["is_enabled"]
          # is_nat_enabled - (optional) is a type of bool
          is_nat_enabled = js_challenge.value["is_nat_enabled"]

          dynamic "challenge_settings" {
            for_each = js_challenge.value.challenge_settings
            content {
              # block_action - (optional) is a type of string
              block_action = challenge_settings.value["block_action"]
              # block_error_page_code - (optional) is a type of string
              block_error_page_code = challenge_settings.value["block_error_page_code"]
              # block_error_page_description - (optional) is a type of string
              block_error_page_description = challenge_settings.value["block_error_page_description"]
              # block_error_page_message - (optional) is a type of string
              block_error_page_message = challenge_settings.value["block_error_page_message"]
              # block_response_code - (optional) is a type of number
              block_response_code = challenge_settings.value["block_response_code"]
              # captcha_footer - (optional) is a type of string
              captcha_footer = challenge_settings.value["captcha_footer"]
              # captcha_header - (optional) is a type of string
              captcha_header = challenge_settings.value["captcha_header"]
              # captcha_submit_label - (optional) is a type of string
              captcha_submit_label = challenge_settings.value["captcha_submit_label"]
              # captcha_title - (optional) is a type of string
              captcha_title = challenge_settings.value["captcha_title"]
            }
          }

          dynamic "criteria" {
            for_each = js_challenge.value.criteria
            content {
              # condition - (required) is a type of string
              condition = criteria.value["condition"]
              # is_case_sensitive - (optional) is a type of bool
              is_case_sensitive = criteria.value["is_case_sensitive"]
              # value - (required) is a type of string
              value = criteria.value["value"]
            }
          }

          dynamic "set_http_header" {
            for_each = js_challenge.value.set_http_header
            content {
              # name - (required) is a type of string
              name = set_http_header.value["name"]
              # value - (required) is a type of string
              value = set_http_header.value["value"]
            }
          }

        }
      }

      dynamic "protection_settings" {
        for_each = waf_config.value.protection_settings
        content {
          # allowed_http_methods - (optional) is a type of list of string
          allowed_http_methods = protection_settings.value["allowed_http_methods"]
          # block_action - (optional) is a type of string
          block_action = protection_settings.value["block_action"]
          # block_error_page_code - (optional) is a type of string
          block_error_page_code = protection_settings.value["block_error_page_code"]
          # block_error_page_description - (optional) is a type of string
          block_error_page_description = protection_settings.value["block_error_page_description"]
          # block_error_page_message - (optional) is a type of string
          block_error_page_message = protection_settings.value["block_error_page_message"]
          # block_response_code - (optional) is a type of number
          block_response_code = protection_settings.value["block_response_code"]
          # is_response_inspected - (optional) is a type of bool
          is_response_inspected = protection_settings.value["is_response_inspected"]
          # max_argument_count - (optional) is a type of number
          max_argument_count = protection_settings.value["max_argument_count"]
          # max_name_length_per_argument - (optional) is a type of number
          max_name_length_per_argument = protection_settings.value["max_name_length_per_argument"]
          # max_response_size_in_ki_b - (optional) is a type of number
          max_response_size_in_ki_b = protection_settings.value["max_response_size_in_ki_b"]
          # max_total_name_length_of_arguments - (optional) is a type of number
          max_total_name_length_of_arguments = protection_settings.value["max_total_name_length_of_arguments"]
          # media_types - (optional) is a type of list of string
          media_types = protection_settings.value["media_types"]
          # recommendations_period_in_days - (optional) is a type of number
          recommendations_period_in_days = protection_settings.value["recommendations_period_in_days"]
        }
      }

      dynamic "whitelists" {
        for_each = waf_config.value.whitelists
        content {
          # address_lists - (optional) is a type of list of string
          address_lists = whitelists.value["address_lists"]
          # addresses - (optional) is a type of list of string
          addresses = whitelists.value["addresses"]
          # name - (required) is a type of string
          name = whitelists.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "additional_domains" {
  description = "returns a list of string"
  value       = oci_waas_waas_policy.this.additional_domains
}

output "cname" {
  description = "returns a string"
  value       = oci_waas_waas_policy.this.cname
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_waas_waas_policy.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_waas_waas_policy.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_waas_waas_policy.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_waas_waas_policy.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_waas_waas_policy.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_waas_waas_policy.this.time_created
}

output "this" {
  value = oci_waas_waas_policy.this
}
```

[top](#index)