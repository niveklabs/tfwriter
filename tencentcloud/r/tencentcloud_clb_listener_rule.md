# tencentcloud_clb_listener_rule

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_clb_listener_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_listener_rule"

  # certificate_ca_id - (optional) is a type of string
  certificate_ca_id = null
  # certificate_id - (optional) is a type of string
  certificate_id = null
  # certificate_ssl_mode - (optional) is a type of string
  certificate_ssl_mode = null
  # clb_id - (required) is a type of string
  clb_id = null
  # domain - (required) is a type of string
  domain = null
  # forward_type - (optional) is a type of string
  forward_type = null
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = null
  # health_check_http_code - (optional) is a type of number
  health_check_http_code = null
  # health_check_http_domain - (optional) is a type of string
  health_check_http_domain = null
  # health_check_http_method - (optional) is a type of string
  health_check_http_method = null
  # health_check_http_path - (optional) is a type of string
  health_check_http_path = null
  # health_check_interval_time - (optional) is a type of number
  health_check_interval_time = null
  # health_check_switch - (optional) is a type of bool
  health_check_switch = null
  # health_check_unhealth_num - (optional) is a type of number
  health_check_unhealth_num = null
  # http2_switch - (optional) is a type of bool
  http2_switch = null
  # listener_id - (required) is a type of string
  listener_id = null
  # scheduler - (optional) is a type of string
  scheduler = null
  # session_expire_time - (optional) is a type of number
  session_expire_time = null
  # target_type - (optional) is a type of string
  target_type = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_ca_id" {
  description = "(optional) - ID of the client certificate. NOTES: Only supports listeners of HTTPS protocol."
  type        = string
  default     = null
}

variable "certificate_id" {
  description = "(optional) - ID of the server certificate. NOTES: Only supports listeners of HTTPS protocol."
  type        = string
  default     = null
}

variable "certificate_ssl_mode" {
  description = "(optional) - Type of certificate. Valid values: `UNIDIRECTIONAL`, `MUTUAL`. NOTES: Only supports listeners of HTTPS protocol."
  type        = string
  default     = null
}

variable "clb_id" {
  description = "(required) - ID of CLB instance."
  type        = string
}

variable "domain" {
  description = "(required) - Domain name of the listener rule."
  type        = string
}

variable "forward_type" {
  description = "(optional) - Forwarding protocol between the CLB instance and real server. Valid values: `HTTP`, `HTTPS`, `TRPC`."
  type        = string
  default     = null
}

variable "health_check_health_num" {
  description = "(optional) - Health threshold of health check, and the default is `3`. If a success result is returned for the health check 3 consecutive times, indicates that the forwarding is normal. The value range is [2-10]. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "health_check_http_code" {
  description = "(optional) - HTTP Status Code. The default is 31. Valid value ranges: [1~31]. `1 means the return value '1xx' is health. `2` means the return value '2xx' is health. `4` means the return value '3xx' is health. `8` means the return value '4xx' is health. 16 means the return value '5xx' is health. If you want multiple return codes to indicate health, need to add the corresponding values. NOTES: The 'HTTP' health check of the 'TCP' listener only supports specifying one health check status code. NOTES: Only supports listeners of 'HTTP' and 'HTTPS' protocol."
  type        = number
  default     = null
}

variable "health_check_http_domain" {
  description = "(optional) - Domain name of health check. NOTES: Only supports listeners of `HTTP` and `HTTPS` protocol."
  type        = string
  default     = null
}

variable "health_check_http_method" {
  description = "(optional) - Methods of health check. NOTES: Only supports listeners of `HTTP` and `HTTPS` protocol. The default is `HEAD`, the available value are `HEAD` and `GET`."
  type        = string
  default     = null
}

variable "health_check_http_path" {
  description = "(optional) - Path of health check. NOTES: Only supports listeners of `HTTP` and `HTTPS` protocol."
  type        = string
  default     = null
}

variable "health_check_interval_time" {
  description = "(optional) - Interval time of health check. Valid value ranges: (5~300) sec. and the default is `5` sec. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "health_check_switch" {
  description = "(optional) - Indicates whether health check is enabled."
  type        = bool
  default     = null
}

variable "health_check_unhealth_num" {
  description = "(optional) - Unhealthy threshold of health check, and the default is `3`. If the unhealthy result is returned 3 consecutive times, indicates that the forwarding is abnormal. The value range is [2-10].  NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "http2_switch" {
  description = "(optional) - Indicate to apply HTTP2.0 protocol or not."
  type        = bool
  default     = null
}

variable "listener_id" {
  description = "(required) - ID of CLB listener."
  type        = string
}

variable "scheduler" {
  description = "(optional) - Scheduling method of the CLB listener rules. Valid values: `WRR`, `IP HASH`, `LEAST_CONN`. The default is `WRR`.  NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = string
  default     = null
}

variable "session_expire_time" {
  description = "(optional) - Time of session persistence within the CLB listener. NOTES: Available when scheduler is specified as `WRR`, and not available when listener protocol is `TCP_SSL`.  NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "target_type" {
  description = "(optional) - Backend target type. Valid values: `NODE`, `TARGETGROUP`. `NODE` means to bind ordinary nodes, `TARGETGROUP` means to bind target group."
  type        = string
  default     = null
}

variable "url" {
  description = "(required) - Url of the listener rule."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_listener_rule" "this" {
  # certificate_ca_id - (optional) is a type of string
  certificate_ca_id = var.certificate_ca_id
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
  # certificate_ssl_mode - (optional) is a type of string
  certificate_ssl_mode = var.certificate_ssl_mode
  # clb_id - (required) is a type of string
  clb_id = var.clb_id
  # domain - (required) is a type of string
  domain = var.domain
  # forward_type - (optional) is a type of string
  forward_type = var.forward_type
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = var.health_check_health_num
  # health_check_http_code - (optional) is a type of number
  health_check_http_code = var.health_check_http_code
  # health_check_http_domain - (optional) is a type of string
  health_check_http_domain = var.health_check_http_domain
  # health_check_http_method - (optional) is a type of string
  health_check_http_method = var.health_check_http_method
  # health_check_http_path - (optional) is a type of string
  health_check_http_path = var.health_check_http_path
  # health_check_interval_time - (optional) is a type of number
  health_check_interval_time = var.health_check_interval_time
  # health_check_switch - (optional) is a type of bool
  health_check_switch = var.health_check_switch
  # health_check_unhealth_num - (optional) is a type of number
  health_check_unhealth_num = var.health_check_unhealth_num
  # http2_switch - (optional) is a type of bool
  http2_switch = var.http2_switch
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # scheduler - (optional) is a type of string
  scheduler = var.scheduler
  # session_expire_time - (optional) is a type of number
  session_expire_time = var.session_expire_time
  # target_type - (optional) is a type of string
  target_type = var.target_type
  # url - (required) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "forward_type" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.forward_type
}

output "health_check_health_num" {
  description = "returns a number"
  value       = tencentcloud_clb_listener_rule.this.health_check_health_num
}

output "health_check_http_code" {
  description = "returns a number"
  value       = tencentcloud_clb_listener_rule.this.health_check_http_code
}

output "health_check_http_domain" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.health_check_http_domain
}

output "health_check_http_method" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.health_check_http_method
}

output "health_check_http_path" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.health_check_http_path
}

output "health_check_interval_time" {
  description = "returns a number"
  value       = tencentcloud_clb_listener_rule.this.health_check_interval_time
}

output "health_check_switch" {
  description = "returns a bool"
  value       = tencentcloud_clb_listener_rule.this.health_check_switch
}

output "health_check_unhealth_num" {
  description = "returns a number"
  value       = tencentcloud_clb_listener_rule.this.health_check_unhealth_num
}

output "http2_switch" {
  description = "returns a bool"
  value       = tencentcloud_clb_listener_rule.this.http2_switch
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = tencentcloud_clb_listener_rule.this.rule_id
}

output "this" {
  value = tencentcloud_clb_listener_rule.this
}
```

[top](#index)