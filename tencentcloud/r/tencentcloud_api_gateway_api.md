# tencentcloud_api_gateway_api

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
module "tencentcloud_api_gateway_api" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_api"

  # api_desc - (optional) is a type of string
  api_desc = null
  # api_name - (required) is a type of string
  api_name = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # enable_cors - (optional) is a type of bool
  enable_cors = null
  # pre_limit - (optional) is a type of number
  pre_limit = null
  # protocol - (optional) is a type of string
  protocol = null
  # release_limit - (optional) is a type of number
  release_limit = null
  # request_config_method - (optional) is a type of string
  request_config_method = null
  # request_config_path - (required) is a type of string
  request_config_path = null
  # response_fail_example - (optional) is a type of string
  response_fail_example = null
  # response_success_example - (optional) is a type of string
  response_success_example = null
  # response_type - (optional) is a type of string
  response_type = null
  # service_config_method - (optional) is a type of string
  service_config_method = null
  # service_config_mock_return_message - (optional) is a type of string
  service_config_mock_return_message = null
  # service_config_path - (optional) is a type of string
  service_config_path = null
  # service_config_product - (optional) is a type of string
  service_config_product = null
  # service_config_scf_function_name - (optional) is a type of string
  service_config_scf_function_name = null
  # service_config_scf_function_namespace - (optional) is a type of string
  service_config_scf_function_namespace = null
  # service_config_scf_function_qualifier - (optional) is a type of string
  service_config_scf_function_qualifier = null
  # service_config_timeout - (optional) is a type of number
  service_config_timeout = null
  # service_config_type - (optional) is a type of string
  service_config_type = null
  # service_config_url - (optional) is a type of string
  service_config_url = null
  # service_config_vpc_id - (optional) is a type of string
  service_config_vpc_id = null
  # service_id - (required) is a type of string
  service_id = null
  # test_limit - (optional) is a type of number
  test_limit = null

  request_parameters = [{
    default_value = null
    desc          = null
    name          = null
    position      = null
    required      = null
    type          = null
  }]

  response_error_codes = [{
    code           = null
    converted_code = null
    desc           = null
    msg            = null
    need_convert   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_desc" {
  description = "(optional) - Custom API description."
  type        = string
  default     = null
}

variable "api_name" {
  description = "(required) - Custom API name."
  type        = string
}

variable "auth_type" {
  description = "(optional) - API authentication type. Valid values: `SECRET` (key pair authentication),`NONE` (no authentication). Default value: `NONE`."
  type        = string
  default     = null
}

variable "enable_cors" {
  description = "(optional) - Whether to enable CORS. Default value: `true`."
  type        = bool
  default     = null
}

variable "pre_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional) - API frontend request type. Valid values: `HTTP`, `WEBSOCKET`. Default value: `HTTP`."
  type        = string
  default     = null
}

variable "release_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}

variable "request_config_method" {
  description = "(optional) - Request frontend method configuration. Valid values: `GET`,`POST`,`PUT`,`DELETE`,`HEAD`,`ANY`. Default value: `GET`."
  type        = string
  default     = null
}

variable "request_config_path" {
  description = "(required) - Request frontend path configuration. Like `/user/getinfo`."
  type        = string
}

variable "response_fail_example" {
  description = "(optional) - Response failure sample of custom response configuration."
  type        = string
  default     = null
}

variable "response_success_example" {
  description = "(optional) - Successful response sample of custom response configuration."
  type        = string
  default     = null
}

variable "response_type" {
  description = "(optional) - Return type. Valid values: `HTML`, `JSON`, `TEXT`, `BINARY`, `XML`. Default value: `HTML`."
  type        = string
  default     = null
}

variable "service_config_method" {
  description = "(optional) - API backend service request method, such as `GET`. If `service_config_type` is `HTTP`, this parameter will be required. The frontend `request_config_method` and backend method `service_config_method` can be different."
  type        = string
  default     = null
}

variable "service_config_mock_return_message" {
  description = "(optional) - Returned information of API backend mocking. This parameter is required when `service_config_type` is `MOCK`."
  type        = string
  default     = null
}

variable "service_config_path" {
  description = "(optional) - API backend service path, such as /path. If `service_config_type` is `HTTP`, this parameter will be required. The frontend `request_config_path` and backend path `service_config_path` can be different."
  type        = string
  default     = null
}

variable "service_config_product" {
  description = "(optional) - Backend type. This parameter takes effect when VPC is enabled. Currently, only `clb` is supported."
  type        = string
  default     = null
}

variable "service_config_scf_function_name" {
  description = "(optional) - SCF function name. This parameter takes effect when `service_config_type` is `SCF`."
  type        = string
  default     = null
}

variable "service_config_scf_function_namespace" {
  description = "(optional) - SCF function namespace. This parameter takes effect when `service_config_type` is `SCF`."
  type        = string
  default     = null
}

variable "service_config_scf_function_qualifier" {
  description = "(optional) - SCF function version. This parameter takes effect when `service_config_type` is `SCF`."
  type        = string
  default     = null
}

variable "service_config_timeout" {
  description = "(optional) - API backend service timeout period in seconds. Default value: `5`."
  type        = number
  default     = null
}

variable "service_config_type" {
  description = "(optional) - API backend service type. Valid values: `WEBSOCKET`, `HTTP`, `SCF`, `MOCK`. Default value: `HTTP`."
  type        = string
  default     = null
}

variable "service_config_url" {
  description = "(optional) - API backend service url. This parameter is required when `service_config_type` is `HTTP`."
  type        = string
  default     = null
}

variable "service_config_vpc_id" {
  description = "(optional) - Unique VPC ID."
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required) - Which service this API belongs. Refer to resource `tencentcloud_api_gateway_service`."
  type        = string
}

variable "test_limit" {
  description = "(optional) - API QPS value. Enter a positive number to limit the API query rate per second `QPS`."
  type        = number
  default     = null
}

variable "request_parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_value = string
      desc          = string
      name          = string
      position      = string
      required      = bool
      type          = string
    }
  ))
  default = []
}

variable "response_error_codes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      code           = number
      converted_code = number
      desc           = string
      msg            = string
      need_convert   = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_api" "this" {
  api_desc                              = var.api_desc
  api_name                              = var.api_name
  auth_type                             = var.auth_type
  enable_cors                           = var.enable_cors
  pre_limit                             = var.pre_limit
  protocol                              = var.protocol
  release_limit                         = var.release_limit
  request_config_method                 = var.request_config_method
  request_config_path                   = var.request_config_path
  response_fail_example                 = var.response_fail_example
  response_success_example              = var.response_success_example
  response_type                         = var.response_type
  service_config_method                 = var.service_config_method
  service_config_mock_return_message    = var.service_config_mock_return_message
  service_config_path                   = var.service_config_path
  service_config_product                = var.service_config_product
  service_config_scf_function_name      = var.service_config_scf_function_name
  service_config_scf_function_namespace = var.service_config_scf_function_namespace
  service_config_scf_function_qualifier = var.service_config_scf_function_qualifier
  service_config_timeout                = var.service_config_timeout
  service_config_type                   = var.service_config_type
  service_config_url                    = var.service_config_url
  service_config_vpc_id                 = var.service_config_vpc_id
  service_id                            = var.service_id
  test_limit                            = var.test_limit

  dynamic "request_parameters" {
    for_each = var.request_parameters
    content {
      default_value = request_parameters.value["default_value"]
      desc          = request_parameters.value["desc"]
      name          = request_parameters.value["name"]
      position      = request_parameters.value["position"]
      required      = request_parameters.value["required"]
      type          = request_parameters.value["type"]
    }
  }

  dynamic "response_error_codes" {
    for_each = var.response_error_codes
    content {
      code           = response_error_codes.value["code"]
      converted_code = response_error_codes.value["converted_code"]
      desc           = response_error_codes.value["desc"]
      msg            = response_error_codes.value["msg"]
      need_convert   = response_error_codes.value["need_convert"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api.this.id
}

output "pre_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_api.this.pre_limit
}

output "release_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_api.this.release_limit
}

output "response_type" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api.this.response_type
}

output "test_limit" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_api.this.test_limit
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api.this.update_time
}

output "this" {
  value = tencentcloud_api_gateway_api.this
}
```

[top](#index)