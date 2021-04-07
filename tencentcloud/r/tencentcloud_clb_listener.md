# tencentcloud_clb_listener

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
module "tencentcloud_clb_listener" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_listener"

  # certificate_ca_id - (optional) is a type of string
  certificate_ca_id = null
  # certificate_id - (optional) is a type of string
  certificate_id = null
  # certificate_ssl_mode - (optional) is a type of string
  certificate_ssl_mode = null
  # clb_id - (required) is a type of string
  clb_id = null
  # health_check_context_type - (optional) is a type of string
  health_check_context_type = null
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
  # health_check_http_version - (optional) is a type of string
  health_check_http_version = null
  # health_check_interval_time - (optional) is a type of number
  health_check_interval_time = null
  # health_check_port - (optional) is a type of number
  health_check_port = null
  # health_check_recv_context - (optional) is a type of string
  health_check_recv_context = null
  # health_check_send_context - (optional) is a type of string
  health_check_send_context = null
  # health_check_switch - (optional) is a type of bool
  health_check_switch = null
  # health_check_time_out - (optional) is a type of number
  health_check_time_out = null
  # health_check_type - (optional) is a type of string
  health_check_type = null
  # health_check_unhealth_num - (optional) is a type of number
  health_check_unhealth_num = null
  # listener_name - (required) is a type of string
  listener_name = null
  # port - (optional) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # scheduler - (optional) is a type of string
  scheduler = null
  # session_expire_time - (optional) is a type of number
  session_expire_time = null
  # sni_switch - (optional) is a type of bool
  sni_switch = null
  # target_type - (optional) is a type of string
  target_type = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_ca_id" {
  description = "(optional) - ID of the client certificate. NOTES: Only supports listeners of `HTTPS` and `TCP_SSL` protocol and must be set when the ssl mode is `MUTUAL`."
  type        = string
  default     = null
}

variable "certificate_id" {
  description = "(optional) - ID of the server certificate. NOTES: Only supports listeners of `HTTPS` and `TCP_SSL` protocol and must be set when it is available."
  type        = string
  default     = null
}

variable "certificate_ssl_mode" {
  description = "(optional) - Type of certificate. Valid values: `UNIDIRECTIONAL`, `MUTUAL`. NOTES: Only supports listeners of `HTTPS` and `TCP_SSL` protocol and must be set when it is available."
  type        = string
  default     = null
}

variable "clb_id" {
  description = "(required) - ID of the CLB."
  type        = string
}

variable "health_check_context_type" {
  description = "(optional) - Health check protocol. When the value of `health_check_type` of the health check protocol is `CUSTOM`, this field is required, which represents the input format of the health check. Valid values: `HEX`, `TEXT`."
  type        = string
  default     = null
}

variable "health_check_health_num" {
  description = "(optional) - Health threshold of health check, and the default is `3`. If a success result is returned for the health check for 3 consecutive times, the backend CVM is identified as healthy. The value range is 2-10. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in tencentcloud_clb_listener_rule."
  type        = number
  default     = null
}

variable "health_check_http_code" {
  description = "(optional) - HTTP health check code of TCP listener. When the value of `health_check_type` of the health check protocol is `HTTP`, this field is required. Valid values: `1`, `2`, `4`, `8`, `16`. `1` means http_1xx, `2` means http_2xx, `4` means http_3xx, `8` means http_4xx, `16` means http_5xx."
  type        = number
  default     = null
}

variable "health_check_http_domain" {
  description = "(optional) - HTTP health check domain of TCP listener."
  type        = string
  default     = null
}

variable "health_check_http_method" {
  description = "(optional) - HTTP health check method of TCP listener. Valid values: `HEAD`, `GET`."
  type        = string
  default     = null
}

variable "health_check_http_path" {
  description = "(optional) - HTTP health check path of TCP listener."
  type        = string
  default     = null
}

variable "health_check_http_version" {
  description = "(optional) - The HTTP version of the backend service. When the value of `health_check_type` of the health check protocol is `HTTP`, this field is required. Valid values: `HTTP/1.0`, `HTTP/1.1`."
  type        = string
  default     = null
}

variable "health_check_interval_time" {
  description = "(optional) - Interval time of health check. Valid value ranges: [5~300] sec. and the default is 5 sec. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "health_check_port" {
  description = "(optional) - The health check port is the port of the backend service by default. Unless you want to specify a specific port, it is recommended to leave it blank. Only applicable to TCP/UDP listener."
  type        = number
  default     = null
}

variable "health_check_recv_context" {
  description = "(optional) - It represents the result returned by the health check. When the value of `health_check_type` of the health check protocol is `CUSTOM`, this field is required. Only ASCII visible characters are allowed and the maximum length is 500. When `health_check_context_type` value is `HEX`, the characters of SendContext and RecvContext can only be selected in `0123456789ABCDEF` and the length must be even digits."
  type        = string
  default     = null
}

variable "health_check_send_context" {
  description = "(optional) - It represents the content of the request sent by the health check. When the value of `health_check_type` of the health check protocol is `CUSTOM`, this field is required. Only visible ASCII characters are allowed and the maximum length is 500. When `health_check_context_type` value is `HEX`, the characters of SendContext and RecvContext can only be selected in `0123456789ABCDEF` and the length must be even digits."
  type        = string
  default     = null
}

variable "health_check_switch" {
  description = "(optional) - Indicates whether health check is enabled."
  type        = bool
  default     = null
}

variable "health_check_time_out" {
  description = "(optional) - Response timeout of health check. Valid value ranges: [2~60] sec. Default is 2 sec. Response timeout needs to be less than check interval. NOTES: Only supports listeners of `TCP`,`UDP`,`TCP_SSL` protocol."
  type        = number
  default     = null
}

variable "health_check_type" {
  description = "(optional) - Protocol used for health check. Valid values: `CUSTOM`, `TCP`, `HTTP`."
  type        = string
  default     = null
}

variable "health_check_unhealth_num" {
  description = "(optional) - Unhealthy threshold of health check, and the default is `3`. If a success result is returned for the health check 3 consecutive times, the CVM is identified as unhealthy. The value range is [2-10]. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "listener_name" {
  description = "(required) - Name of the CLB listener, and available values can only be Chinese characters, English letters, numbers, underscore and hyphen '-'."
  type        = string
}

variable "port" {
  description = "(optional) - Port of the CLB listener."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required) - Type of protocol within the listener. Valid values: `TCP`, `UDP`, `HTTP`, `HTTPS` and `TCP_SSL`."
  type        = string
}

variable "scheduler" {
  description = "(optional) - Scheduling method of the CLB listener, and available values are 'WRR' and 'LEAST_CONN'. The default is 'WRR'. NOTES: The listener of `HTTP` and `HTTPS` protocol additionally supports the `IP Hash` method. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = string
  default     = null
}

variable "session_expire_time" {
  description = "(optional) - Time of session persistence within the CLB listener. NOTES: Available when scheduler is specified as `WRR`, and not available when listener protocol is `TCP_SSL`. NOTES: TCP/UDP/TCP_SSL listener allows direct configuration, HTTP/HTTPS listener needs to be configured in `tencentcloud_clb_listener_rule`."
  type        = number
  default     = null
}

variable "sni_switch" {
  description = "(optional) - Indicates whether SNI is enabled, and only supported with protocol `HTTPS`. If enabled, you can set a certificate for each rule in `tencentcloud_clb_listener_rule`, otherwise all rules have a certificate."
  type        = bool
  default     = null
}

variable "target_type" {
  description = "(optional) - Backend target type. Valid values: `NODE`, `TARGETGROUP`. `NODE` means to bind ordinary nodes, `TARGETGROUP` means to bind target group. NOTES: TCP/UDP/TCP_SSL listener must configuration, HTTP/HTTPS listener needs to be configured in tencentcloud_clb_listener_rule."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_listener" "this" {
  certificate_ca_id          = var.certificate_ca_id
  certificate_id             = var.certificate_id
  certificate_ssl_mode       = var.certificate_ssl_mode
  clb_id                     = var.clb_id
  health_check_context_type  = var.health_check_context_type
  health_check_health_num    = var.health_check_health_num
  health_check_http_code     = var.health_check_http_code
  health_check_http_domain   = var.health_check_http_domain
  health_check_http_method   = var.health_check_http_method
  health_check_http_path     = var.health_check_http_path
  health_check_http_version  = var.health_check_http_version
  health_check_interval_time = var.health_check_interval_time
  health_check_port          = var.health_check_port
  health_check_recv_context  = var.health_check_recv_context
  health_check_send_context  = var.health_check_send_context
  health_check_switch        = var.health_check_switch
  health_check_time_out      = var.health_check_time_out
  health_check_type          = var.health_check_type
  health_check_unhealth_num  = var.health_check_unhealth_num
  listener_name              = var.listener_name
  port                       = var.port
  protocol                   = var.protocol
  scheduler                  = var.scheduler
  session_expire_time        = var.session_expire_time
  sni_switch                 = var.sni_switch
  target_type                = var.target_type
}
```

[top](#index)

### Outputs

```terraform
output "health_check_health_num" {
  description = "returns a number"
  value       = tencentcloud_clb_listener.this.health_check_health_num
}

output "health_check_http_method" {
  description = "returns a string"
  value       = tencentcloud_clb_listener.this.health_check_http_method
}

output "health_check_interval_time" {
  description = "returns a number"
  value       = tencentcloud_clb_listener.this.health_check_interval_time
}

output "health_check_switch" {
  description = "returns a bool"
  value       = tencentcloud_clb_listener.this.health_check_switch
}

output "health_check_time_out" {
  description = "returns a number"
  value       = tencentcloud_clb_listener.this.health_check_time_out
}

output "health_check_type" {
  description = "returns a string"
  value       = tencentcloud_clb_listener.this.health_check_type
}

output "health_check_unhealth_num" {
  description = "returns a number"
  value       = tencentcloud_clb_listener.this.health_check_unhealth_num
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_listener.this.id
}

output "listener_id" {
  description = "returns a string"
  value       = tencentcloud_clb_listener.this.listener_id
}

output "this" {
  value = tencentcloud_clb_listener.this
}
```

[top](#index)