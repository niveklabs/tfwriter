# avi_wafprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_wafprofile" {
  source = "./modules/avi/r/avi_wafprofile"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  config = [{
    allowed_http_versions         = []
    allowed_methods               = []
    allowed_request_content_types = []
    argument_separator            = null
    client_request_max_body_size  = null
    confidence_override = [{
      confid_high_value      = null
      confid_low_value       = null
      confid_probable_value  = null
      confid_very_high_value = null
    }]
    cookie_format_version                = null
    enable_auto_rule_updates             = null
    ignore_incomplete_request_body_error = null
    learning_params = [{
      enable_per_uri_learning = null
      max_params              = null
      max_uris                = null
      min_hits_to_learn       = null
      sampling_percent        = null
      update_interval         = null
    }]
    max_execution_time                = null
    min_confidence                    = null
    regex_match_limit                 = null
    regex_recursion_limit             = null
    request_body_default_action       = null
    request_hdr_default_action        = null
    response_body_default_action      = null
    response_hdr_default_action       = null
    restricted_extensions             = []
    restricted_headers                = []
    server_response_max_body_size     = null
    static_extensions                 = []
    status_code_for_rejected_requests = null
  }]

  files = [{
    data = null
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_http_versions         = list(string)
      allowed_methods               = list(string)
      allowed_request_content_types = list(string)
      argument_separator            = string
      client_request_max_body_size  = number
      confidence_override = set(object(
        {
          confid_high_value      = number
          confid_low_value       = number
          confid_probable_value  = number
          confid_very_high_value = number
        }
      ))
      cookie_format_version                = number
      enable_auto_rule_updates             = bool
      ignore_incomplete_request_body_error = bool
      learning_params = set(object(
        {
          enable_per_uri_learning = bool
          max_params              = number
          max_uris                = number
          min_hits_to_learn       = number
          sampling_percent        = number
          update_interval         = number
        }
      ))
      max_execution_time                = number
      min_confidence                    = string
      regex_match_limit                 = number
      regex_recursion_limit             = number
      request_body_default_action       = string
      request_hdr_default_action        = string
      response_body_default_action      = string
      response_hdr_default_action       = string
      restricted_extensions             = list(string)
      restricted_headers                = list(string)
      server_response_max_body_size     = number
      static_extensions                 = list(string)
      status_code_for_rejected_requests = string
    }
  ))
  default = []
}

variable "files" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_wafprofile" "this" {
  description = var.description
  name        = var.name
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid

  dynamic "config" {
    for_each = var.config
    content {
      allowed_http_versions                = config.value["allowed_http_versions"]
      allowed_methods                      = config.value["allowed_methods"]
      allowed_request_content_types        = config.value["allowed_request_content_types"]
      argument_separator                   = config.value["argument_separator"]
      client_request_max_body_size         = config.value["client_request_max_body_size"]
      cookie_format_version                = config.value["cookie_format_version"]
      enable_auto_rule_updates             = config.value["enable_auto_rule_updates"]
      ignore_incomplete_request_body_error = config.value["ignore_incomplete_request_body_error"]
      max_execution_time                   = config.value["max_execution_time"]
      min_confidence                       = config.value["min_confidence"]
      regex_match_limit                    = config.value["regex_match_limit"]
      regex_recursion_limit                = config.value["regex_recursion_limit"]
      request_body_default_action          = config.value["request_body_default_action"]
      request_hdr_default_action           = config.value["request_hdr_default_action"]
      response_body_default_action         = config.value["response_body_default_action"]
      response_hdr_default_action          = config.value["response_hdr_default_action"]
      restricted_extensions                = config.value["restricted_extensions"]
      restricted_headers                   = config.value["restricted_headers"]
      server_response_max_body_size        = config.value["server_response_max_body_size"]
      static_extensions                    = config.value["static_extensions"]
      status_code_for_rejected_requests    = config.value["status_code_for_rejected_requests"]

      dynamic "confidence_override" {
        for_each = config.value.confidence_override
        content {
          confid_high_value      = confidence_override.value["confid_high_value"]
          confid_low_value       = confidence_override.value["confid_low_value"]
          confid_probable_value  = confidence_override.value["confid_probable_value"]
          confid_very_high_value = confidence_override.value["confid_very_high_value"]
        }
      }

      dynamic "learning_params" {
        for_each = config.value.learning_params
        content {
          enable_per_uri_learning = learning_params.value["enable_per_uri_learning"]
          max_params              = learning_params.value["max_params"]
          max_uris                = learning_params.value["max_uris"]
          min_hits_to_learn       = learning_params.value["min_hits_to_learn"]
          sampling_percent        = learning_params.value["sampling_percent"]
          update_interval         = learning_params.value["update_interval"]
        }
      }

    }
  }

  dynamic "files" {
    for_each = var.files
    content {
      data = files.value["data"]
      name = files.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_wafprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_wafprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_wafprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_wafprofile.this.uuid
}

output "this" {
  value = avi_wafprofile.this
}
```

[top](#index)