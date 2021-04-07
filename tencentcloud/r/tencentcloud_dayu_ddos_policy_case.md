# tencentcloud_dayu_ddos_policy_case

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
module "tencentcloud_dayu_ddos_policy_case" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_ddos_policy_case"

  # app_protocols - (required) is a type of set of string
  app_protocols = []
  # app_type - (required) is a type of string
  app_type = null
  # has_abroad - (required) is a type of string
  has_abroad = null
  # has_initiate_tcp - (required) is a type of string
  has_initiate_tcp = null
  # has_initiate_udp - (optional) is a type of string
  has_initiate_udp = null
  # has_vpn - (optional) is a type of string
  has_vpn = null
  # max_tcp_package_len - (optional) is a type of string
  max_tcp_package_len = null
  # max_udp_package_len - (optional) is a type of string
  max_udp_package_len = null
  # min_tcp_package_len - (optional) is a type of string
  min_tcp_package_len = null
  # min_udp_package_len - (optional) is a type of string
  min_udp_package_len = null
  # name - (required) is a type of string
  name = null
  # peer_tcp_port - (optional) is a type of string
  peer_tcp_port = null
  # peer_udp_port - (optional) is a type of string
  peer_udp_port = null
  # platform_types - (required) is a type of set of string
  platform_types = []
  # resource_type - (required) is a type of string
  resource_type = null
  # tcp_end_port - (required) is a type of string
  tcp_end_port = null
  # tcp_footprint - (optional) is a type of string
  tcp_footprint = null
  # tcp_start_port - (required) is a type of string
  tcp_start_port = null
  # udp_end_port - (required) is a type of string
  udp_end_port = null
  # udp_footprint - (optional) is a type of string
  udp_footprint = null
  # udp_start_port - (required) is a type of string
  udp_start_port = null
  # web_api_urls - (required) is a type of set of string
  web_api_urls = []
}
```

[top](#index)

### Variables

```terraform
variable "app_protocols" {
  description = "(required) - App protocol set of the DDoS policy case."
  type        = set(string)
}

variable "app_type" {
  description = "(required) - App type of the DDoS policy case. Valid values: `WEB`, `GAME`, `APP` and `OTHER`."
  type        = string
}

variable "has_abroad" {
  description = "(required) - Indicate whether the service involves overseas or not. Valid values: `no` and `yes`."
  type        = string
}

variable "has_initiate_tcp" {
  description = "(required) - Indicate whether the service actively initiates TCP requests or not. Valid values: `no` and `yes`."
  type        = string
}

variable "has_initiate_udp" {
  description = "(optional) - Indicate whether the actively initiate UDP requests or not. Valid values: `no` and `yes`."
  type        = string
  default     = null
}

variable "has_vpn" {
  description = "(optional) - Indicate whether the service involves VPN service or not. Valid values: `no` and `yes`."
  type        = string
  default     = null
}

variable "max_tcp_package_len" {
  description = "(optional) - The max length of TCP message package, valid value length should be greater than 0 and less than 1500. It should be greater than `min_tcp_package_len`."
  type        = string
  default     = null
}

variable "max_udp_package_len" {
  description = "(optional) - The max length of UDP message package, valid value length should be greater than 0 and less than 1500. It should be greater than `min_udp_package_len`."
  type        = string
  default     = null
}

variable "min_tcp_package_len" {
  description = "(optional) - The minimum length of TCP message package, valid value length should be greater than 0 and less than 1500."
  type        = string
  default     = null
}

variable "min_udp_package_len" {
  description = "(optional) - The minimum length of UDP message package, valid value length should be greater than 0 and less than 1500."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the DDoS policy case. Length should between 1 and 64."
  type        = string
}

variable "peer_tcp_port" {
  description = "(optional) - The port that actively initiates TCP requests. Valid value ranges: (1~65535)."
  type        = string
  default     = null
}

variable "peer_udp_port" {
  description = "(optional) - The port that actively initiates UDP requests. Valid value ranges: (1~65535)."
  type        = string
  default     = null
}

variable "platform_types" {
  description = "(required) - Platform set of the DDoS policy case."
  type        = set(string)
}

variable "resource_type" {
  description = "(required) - Type of the resource that the DDoS policy case works for. Valid values: `bgpip`, `bgp` and `bgp-multip`."
  type        = string
}

variable "tcp_end_port" {
  description = "(required) - End port of the TCP service. Valid value ranges: (0~65535). It must be greater than `tcp_start_port`."
  type        = string
}

variable "tcp_footprint" {
  description = "(optional) - The fixed signature of TCP protocol load, valid value length is range from 1 to 512."
  type        = string
  default     = null
}

variable "tcp_start_port" {
  description = "(required) - Start port of the TCP service. Valid value ranges: (0~65535)."
  type        = string
}

variable "udp_end_port" {
  description = "(required) - End port of the UDP service. Valid value ranges: (0~65535). It must be greater than `udp_start_port`."
  type        = string
}

variable "udp_footprint" {
  description = "(optional) - The fixed signature of TCP protocol load, valid value length is range from 1 to 512."
  type        = string
  default     = null
}

variable "udp_start_port" {
  description = "(required) - Start port of the UDP service. Valid value ranges: (0~65535)."
  type        = string
}

variable "web_api_urls" {
  description = "(required) - Web API url set."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_ddos_policy_case" "this" {
  app_protocols       = var.app_protocols
  app_type            = var.app_type
  has_abroad          = var.has_abroad
  has_initiate_tcp    = var.has_initiate_tcp
  has_initiate_udp    = var.has_initiate_udp
  has_vpn             = var.has_vpn
  max_tcp_package_len = var.max_tcp_package_len
  max_udp_package_len = var.max_udp_package_len
  min_tcp_package_len = var.min_tcp_package_len
  min_udp_package_len = var.min_udp_package_len
  name                = var.name
  peer_tcp_port       = var.peer_tcp_port
  peer_udp_port       = var.peer_udp_port
  platform_types      = var.platform_types
  resource_type       = var.resource_type
  tcp_end_port        = var.tcp_end_port
  tcp_footprint       = var.tcp_footprint
  tcp_start_port      = var.tcp_start_port
  udp_end_port        = var.udp_end_port
  udp_footprint       = var.udp_footprint
  udp_start_port      = var.udp_start_port
  web_api_urls        = var.web_api_urls
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy_case.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy_case.this.id
}

output "scene_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_ddos_policy_case.this.scene_id
}

output "this" {
  value = tencentcloud_dayu_ddos_policy_case.this
}
```

[top](#index)