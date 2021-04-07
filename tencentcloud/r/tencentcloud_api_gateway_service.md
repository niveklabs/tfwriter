# tencentcloud_api_gateway_service

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
module "tencentcloud_api_gateway_service" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_service"

  # exclusive_set_name - (optional) is a type of string
  exclusive_set_name = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # net_type - (required) is a type of set of string
  net_type = []
  # pre_limit - (optional) is a type of number
  pre_limit = null
  # protocol - (required) is a type of string
  protocol = null
  # release_limit - (optional) is a type of number
  release_limit = null
  # service_desc - (optional) is a type of string
  service_desc = null
  # service_name - (required) is a type of string
  service_name = null
  # test_limit - (optional) is a type of number
  test_limit = null
}
```

[top](#index)

### Variables

```terraform
variable "exclusive_set_name" {
  description = "(optional) - Self-deployed cluster name, which is used to specify the self-deployed cluster where the service is to be created."
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional) - IP version number. Valid values: `IPv4`, `IPv6`. Default value: `IPv4`."
  type        = string
  default     = null
}

variable "net_type" {
  description = "(required) - Network type list, which is used to specify the supported network types. Valid values: `INNER`, `OUTER`. `INNER` indicates access over private network, and `OUTER` indicates access over public network."
  type        = set(string)
}

variable "pre_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required) - Service frontend request type. Valid values: `http`, `https`, `http&https`."
  type        = string
}

variable "release_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}

variable "service_desc" {
  description = "(optional) - Custom service description."
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required) - Custom service name."
  type        = string
}

variable "test_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_service" "this" {
  exclusive_set_name = var.exclusive_set_name
  ip_version         = var.ip_version
  net_type           = var.net_type
  pre_limit          = var.pre_limit
  protocol           = var.protocol
  release_limit      = var.release_limit
  service_desc       = var.service_desc
  service_name       = var.service_name
  test_limit         = var.test_limit
}
```

[top](#index)

### Outputs

```terraform
output "api_list" {
  description = "returns a list of object"
  value       = tencentcloud_api_gateway_service.this.api_list
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service.this.id
}

output "inner_http_port" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_service.this.inner_http_port
}

output "inner_https_port" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_service.this.inner_https_port
}

output "internal_sub_domain" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service.this.internal_sub_domain
}

output "modify_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service.this.modify_time
}

output "outer_sub_domain" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_service.this.outer_sub_domain
}

output "pre_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_service.this.pre_limit
}

output "release_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_service.this.release_limit
}

output "test_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_service.this.test_limit
}

output "usage_plan_list" {
  description = "returns a list of object"
  value       = tencentcloud_api_gateway_service.this.usage_plan_list
}

output "this" {
  value = tencentcloud_api_gateway_service.this
}
```

[top](#index)