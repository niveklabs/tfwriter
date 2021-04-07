# thunder_slb_resource_usage

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_resource_usage" {
  source = "./modules/thunder/r/thunder_slb_resource_usage"

  # cache_template_count - (optional) is a type of number
  cache_template_count = null
  # client_ssl_template_count - (optional) is a type of number
  client_ssl_template_count = null
  # conn_reuse_template_count - (optional) is a type of number
  conn_reuse_template_count = null
  # fast_tcp_template_count - (optional) is a type of number
  fast_tcp_template_count = null
  # fast_udp_template_count - (optional) is a type of number
  fast_udp_template_count = null
  # health_monitor_count - (optional) is a type of number
  health_monitor_count = null
  # http_template_count - (optional) is a type of number
  http_template_count = null
  # nat_pool_addr_count - (optional) is a type of number
  nat_pool_addr_count = null
  # pbslb_subnet_count - (optional) is a type of number
  pbslb_subnet_count = null
  # persist_cookie_template_count - (optional) is a type of number
  persist_cookie_template_count = null
  # persist_srcip_template_count - (optional) is a type of number
  persist_srcip_template_count = null
  # proxy_template_count - (optional) is a type of number
  proxy_template_count = null
  # real_port_count - (optional) is a type of number
  real_port_count = null
  # real_server_count - (optional) is a type of number
  real_server_count = null
  # server_ssl_template_count - (optional) is a type of number
  server_ssl_template_count = null
  # service_group_count - (optional) is a type of number
  service_group_count = null
  # slb_threshold_res_usage_percent - (optional) is a type of number
  slb_threshold_res_usage_percent = null
  # stream_template_count - (optional) is a type of number
  stream_template_count = null
  # virtual_port_count - (optional) is a type of number
  virtual_port_count = null
  # virtual_server_count - (optional) is a type of number
  virtual_server_count = null
}
```

[top](#index)

### Variables

```terraform
variable "cache_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_ssl_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_reuse_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fast_tcp_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fast_udp_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_monitor_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nat_pool_addr_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pbslb_subnet_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "persist_cookie_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "persist_srcip_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "real_port_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "real_server_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_ssl_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slb_threshold_res_usage_percent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stream_template_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "virtual_port_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "virtual_server_count" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_resource_usage" "this" {
  # cache_template_count - (optional) is a type of number
  cache_template_count = var.cache_template_count
  # client_ssl_template_count - (optional) is a type of number
  client_ssl_template_count = var.client_ssl_template_count
  # conn_reuse_template_count - (optional) is a type of number
  conn_reuse_template_count = var.conn_reuse_template_count
  # fast_tcp_template_count - (optional) is a type of number
  fast_tcp_template_count = var.fast_tcp_template_count
  # fast_udp_template_count - (optional) is a type of number
  fast_udp_template_count = var.fast_udp_template_count
  # health_monitor_count - (optional) is a type of number
  health_monitor_count = var.health_monitor_count
  # http_template_count - (optional) is a type of number
  http_template_count = var.http_template_count
  # nat_pool_addr_count - (optional) is a type of number
  nat_pool_addr_count = var.nat_pool_addr_count
  # pbslb_subnet_count - (optional) is a type of number
  pbslb_subnet_count = var.pbslb_subnet_count
  # persist_cookie_template_count - (optional) is a type of number
  persist_cookie_template_count = var.persist_cookie_template_count
  # persist_srcip_template_count - (optional) is a type of number
  persist_srcip_template_count = var.persist_srcip_template_count
  # proxy_template_count - (optional) is a type of number
  proxy_template_count = var.proxy_template_count
  # real_port_count - (optional) is a type of number
  real_port_count = var.real_port_count
  # real_server_count - (optional) is a type of number
  real_server_count = var.real_server_count
  # server_ssl_template_count - (optional) is a type of number
  server_ssl_template_count = var.server_ssl_template_count
  # service_group_count - (optional) is a type of number
  service_group_count = var.service_group_count
  # slb_threshold_res_usage_percent - (optional) is a type of number
  slb_threshold_res_usage_percent = var.slb_threshold_res_usage_percent
  # stream_template_count - (optional) is a type of number
  stream_template_count = var.stream_template_count
  # virtual_port_count - (optional) is a type of number
  virtual_port_count = var.virtual_port_count
  # virtual_server_count - (optional) is a type of number
  virtual_server_count = var.virtual_server_count
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_resource_usage.this.id
}

output "this" {
  value = thunder_slb_resource_usage.this
}
```

[top](#index)