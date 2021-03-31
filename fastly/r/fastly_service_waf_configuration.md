# fastly_service_waf_configuration

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_waf_configuration" {
  source = "./modules/fastly/r/fastly_service_waf_configuration"

  # allowed_http_versions - (optional) is a type of string
  allowed_http_versions = null
  # allowed_methods - (optional) is a type of string
  allowed_methods = null
  # allowed_request_content_type - (optional) is a type of string
  allowed_request_content_type = null
  # allowed_request_content_type_charset - (optional) is a type of string
  allowed_request_content_type_charset = null
  # arg_length - (optional) is a type of number
  arg_length = null
  # arg_name_length - (optional) is a type of number
  arg_name_length = null
  # combined_file_sizes - (optional) is a type of number
  combined_file_sizes = null
  # critical_anomaly_score - (optional) is a type of number
  critical_anomaly_score = null
  # crs_validate_utf8_encoding - (optional) is a type of bool
  crs_validate_utf8_encoding = null
  # error_anomaly_score - (optional) is a type of number
  error_anomaly_score = null
  # high_risk_country_codes - (optional) is a type of string
  high_risk_country_codes = null
  # http_violation_score_threshold - (optional) is a type of number
  http_violation_score_threshold = null
  # inbound_anomaly_score_threshold - (optional) is a type of number
  inbound_anomaly_score_threshold = null
  # lfi_score_threshold - (optional) is a type of number
  lfi_score_threshold = null
  # max_file_size - (optional) is a type of number
  max_file_size = null
  # max_num_args - (optional) is a type of number
  max_num_args = null
  # notice_anomaly_score - (optional) is a type of number
  notice_anomaly_score = null
  # paranoia_level - (optional) is a type of number
  paranoia_level = null
  # php_injection_score_threshold - (optional) is a type of number
  php_injection_score_threshold = null
  # rce_score_threshold - (optional) is a type of number
  rce_score_threshold = null
  # restricted_extensions - (optional) is a type of string
  restricted_extensions = null
  # restricted_headers - (optional) is a type of string
  restricted_headers = null
  # rfi_score_threshold - (optional) is a type of number
  rfi_score_threshold = null
  # session_fixation_score_threshold - (optional) is a type of number
  session_fixation_score_threshold = null
  # sql_injection_score_threshold - (optional) is a type of number
  sql_injection_score_threshold = null
  # total_arg_length - (optional) is a type of number
  total_arg_length = null
  # waf_id - (required) is a type of string
  waf_id = null
  # warning_anomaly_score - (optional) is a type of number
  warning_anomaly_score = null
  # xss_score_threshold - (optional) is a type of number
  xss_score_threshold = null

  rule = [{
    modsec_rule_id = null
    revision       = null
    status         = null
  }]

  rule_exclusion = [{
    condition       = null
    exclusion_type  = null
    modsec_rule_ids = []
    name            = null
    number          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowed_http_versions" {
  description = "(optional) - Allowed HTTP versions"
  type        = string
  default     = null
}

variable "allowed_methods" {
  description = "(optional) - A space-separated list of HTTP method names"
  type        = string
  default     = null
}

variable "allowed_request_content_type" {
  description = "(optional) - Allowed request content types"
  type        = string
  default     = null
}

variable "allowed_request_content_type_charset" {
  description = "(optional) - Allowed request content type charset"
  type        = string
  default     = null
}

variable "arg_length" {
  description = "(optional) - The maximum number of arguments allowed"
  type        = number
  default     = null
}

variable "arg_name_length" {
  description = "(optional) - The maximum allowed argument name length"
  type        = number
  default     = null
}

variable "combined_file_sizes" {
  description = "(optional) - The maximum allowed size of all files"
  type        = number
  default     = null
}

variable "critical_anomaly_score" {
  description = "(optional) - Score value to add for critical anomalies"
  type        = number
  default     = null
}

variable "crs_validate_utf8_encoding" {
  description = "(optional) - CRS validate UTF8 encoding"
  type        = bool
  default     = null
}

variable "error_anomaly_score" {
  description = "(optional) - Score value to add for error anomalies"
  type        = number
  default     = null
}

variable "high_risk_country_codes" {
  description = "(optional) - A space-separated list of country codes in ISO 3166-1 (two-letter) format"
  type        = string
  default     = null
}

variable "http_violation_score_threshold" {
  description = "(optional) - HTTP violation threshold"
  type        = number
  default     = null
}

variable "inbound_anomaly_score_threshold" {
  description = "(optional) - Inbound anomaly threshold"
  type        = number
  default     = null
}

variable "lfi_score_threshold" {
  description = "(optional) - Local file inclusion attack threshold"
  type        = number
  default     = null
}

variable "max_file_size" {
  description = "(optional) - The maximum allowed file size, in bytes"
  type        = number
  default     = null
}

variable "max_num_args" {
  description = "(optional) - The maximum number of arguments allowed"
  type        = number
  default     = null
}

variable "notice_anomaly_score" {
  description = "(optional) - Score value to add for notice anomalies"
  type        = number
  default     = null
}

variable "paranoia_level" {
  description = "(optional) - The configured paranoia level"
  type        = number
  default     = null
}

variable "php_injection_score_threshold" {
  description = "(optional) - PHP injection threshold"
  type        = number
  default     = null
}

variable "rce_score_threshold" {
  description = "(optional) - Remote code execution threshold"
  type        = number
  default     = null
}

variable "restricted_extensions" {
  description = "(optional) - A space-separated list of allowed file extensions"
  type        = string
  default     = null
}

variable "restricted_headers" {
  description = "(optional) - A space-separated list of allowed header names"
  type        = string
  default     = null
}

variable "rfi_score_threshold" {
  description = "(optional) - Remote file inclusion attack threshold"
  type        = number
  default     = null
}

variable "session_fixation_score_threshold" {
  description = "(optional) - Session fixation attack threshold"
  type        = number
  default     = null
}

variable "sql_injection_score_threshold" {
  description = "(optional) - SQL injection attack threshold"
  type        = number
  default     = null
}

variable "total_arg_length" {
  description = "(optional) - The maximum size of argument names and values"
  type        = number
  default     = null
}

variable "waf_id" {
  description = "(required) - The ID of the Web Application Firewall that the configuration belongs to"
  type        = string
}

variable "warning_anomaly_score" {
  description = "(optional) - Score value to add for warning anomalies"
  type        = number
  default     = null
}

variable "xss_score_threshold" {
  description = "(optional) - XSS attack threshold"
  type        = number
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      modsec_rule_id = number
      revision       = number
      status         = string
    }
  ))
  default = []
}

variable "rule_exclusion" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      condition       = string
      exclusion_type  = string
      modsec_rule_ids = set(number)
      name            = string
      number          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_waf_configuration" "this" {
  allowed_http_versions                = var.allowed_http_versions
  allowed_methods                      = var.allowed_methods
  allowed_request_content_type         = var.allowed_request_content_type
  allowed_request_content_type_charset = var.allowed_request_content_type_charset
  arg_length                           = var.arg_length
  arg_name_length                      = var.arg_name_length
  combined_file_sizes                  = var.combined_file_sizes
  critical_anomaly_score               = var.critical_anomaly_score
  crs_validate_utf8_encoding           = var.crs_validate_utf8_encoding
  error_anomaly_score                  = var.error_anomaly_score
  high_risk_country_codes              = var.high_risk_country_codes
  http_violation_score_threshold       = var.http_violation_score_threshold
  inbound_anomaly_score_threshold      = var.inbound_anomaly_score_threshold
  lfi_score_threshold                  = var.lfi_score_threshold
  max_file_size                        = var.max_file_size
  max_num_args                         = var.max_num_args
  notice_anomaly_score                 = var.notice_anomaly_score
  paranoia_level                       = var.paranoia_level
  php_injection_score_threshold        = var.php_injection_score_threshold
  rce_score_threshold                  = var.rce_score_threshold
  restricted_extensions                = var.restricted_extensions
  restricted_headers                   = var.restricted_headers
  rfi_score_threshold                  = var.rfi_score_threshold
  session_fixation_score_threshold     = var.session_fixation_score_threshold
  sql_injection_score_threshold        = var.sql_injection_score_threshold
  total_arg_length                     = var.total_arg_length
  waf_id                               = var.waf_id
  warning_anomaly_score                = var.warning_anomaly_score
  xss_score_threshold                  = var.xss_score_threshold

  dynamic "rule" {
    for_each = var.rule
    content {
      modsec_rule_id = rule.value["modsec_rule_id"]
      revision       = rule.value["revision"]
      status         = rule.value["status"]
    }
  }

  dynamic "rule_exclusion" {
    for_each = var.rule_exclusion
    content {
      condition       = rule_exclusion.value["condition"]
      exclusion_type  = rule_exclusion.value["exclusion_type"]
      modsec_rule_ids = rule_exclusion.value["modsec_rule_ids"]
      name            = rule_exclusion.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowed_http_versions" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.allowed_http_versions
}

output "allowed_methods" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.allowed_methods
}

output "allowed_request_content_type" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.allowed_request_content_type
}

output "allowed_request_content_type_charset" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.allowed_request_content_type_charset
}

output "arg_length" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.arg_length
}

output "arg_name_length" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.arg_name_length
}

output "combined_file_sizes" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.combined_file_sizes
}

output "critical_anomaly_score" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.critical_anomaly_score
}

output "crs_validate_utf8_encoding" {
  description = "returns a bool"
  value       = fastly_service_waf_configuration.this.crs_validate_utf8_encoding
}

output "error_anomaly_score" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.error_anomaly_score
}

output "high_risk_country_codes" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.high_risk_country_codes
}

output "http_violation_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.http_violation_score_threshold
}

output "id" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.id
}

output "inbound_anomaly_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.inbound_anomaly_score_threshold
}

output "lfi_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.lfi_score_threshold
}

output "max_file_size" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.max_file_size
}

output "max_num_args" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.max_num_args
}

output "notice_anomaly_score" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.notice_anomaly_score
}

output "paranoia_level" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.paranoia_level
}

output "php_injection_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.php_injection_score_threshold
}

output "rce_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.rce_score_threshold
}

output "restricted_extensions" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.restricted_extensions
}

output "restricted_headers" {
  description = "returns a string"
  value       = fastly_service_waf_configuration.this.restricted_headers
}

output "rfi_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.rfi_score_threshold
}

output "session_fixation_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.session_fixation_score_threshold
}

output "sql_injection_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.sql_injection_score_threshold
}

output "total_arg_length" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.total_arg_length
}

output "warning_anomaly_score" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.warning_anomaly_score
}

output "xss_score_threshold" {
  description = "returns a number"
  value       = fastly_service_waf_configuration.this.xss_score_threshold
}

output "this" {
  value = fastly_service_waf_configuration.this
}
```

[top](#index)