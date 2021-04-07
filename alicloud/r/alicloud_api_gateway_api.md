# alicloud_api_gateway_api

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_api_gateway_api" {
  source = "./modules/alicloud/r/alicloud_api_gateway_api"

  # auth_type - (required) is a type of string
  auth_type = null
  # description - (required) is a type of string
  description = null
  # group_id - (required) is a type of string
  group_id = null
  # name - (required) is a type of string
  name = null
  # service_type - (required) is a type of string
  service_type = null
  # stage_names - (optional) is a type of set of string
  stage_names = []

  constant_parameters = [{
    description = null
    in          = null
    name        = null
    value       = null
  }]

  fc_service_config = [{
    arn_role      = null
    function_name = null
    region        = null
    service_name  = null
    timeout       = null
  }]

  http_service_config = [{
    address   = null
    aone_name = null
    method    = null
    path      = null
    timeout   = null
  }]

  http_vpc_service_config = [{
    aone_name = null
    method    = null
    name      = null
    path      = null
    timeout   = null
  }]

  mock_service_config = [{
    aone_name = null
    result    = null
  }]

  request_config = [{
    body_format = null
    method      = null
    mode        = null
    path        = null
    protocol    = null
  }]

  request_parameters = [{
    default_value = null
    description   = null
    in            = null
    in_service    = null
    name          = null
    name_service  = null
    required      = null
    type          = null
  }]

  system_parameters = [{
    in           = null
    name         = null
    name_service = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "service_type" {
  description = "(required)"
  type        = string
}

variable "stage_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "constant_parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      in          = string
      name        = string
      value       = string
    }
  ))
  default = []
}

variable "fc_service_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn_role      = string
      function_name = string
      region        = string
      service_name  = string
      timeout       = number
    }
  ))
  default = []
}

variable "http_service_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address   = string
      aone_name = string
      method    = string
      path      = string
      timeout   = number
    }
  ))
  default = []
}

variable "http_vpc_service_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aone_name = string
      method    = string
      name      = string
      path      = string
      timeout   = number
    }
  ))
  default = []
}

variable "mock_service_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aone_name = string
      result    = string
    }
  ))
  default = []
}

variable "request_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      body_format = string
      method      = string
      mode        = string
      path        = string
      protocol    = string
    }
  ))
}

variable "request_parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_value = string
      description   = string
      in            = string
      in_service    = string
      name          = string
      name_service  = string
      required      = string
      type          = string
    }
  ))
  default = []
}

variable "system_parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      in           = string
      name         = string
      name_service = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_api_gateway_api" "this" {
  # auth_type - (required) is a type of string
  auth_type = var.auth_type
  # description - (required) is a type of string
  description = var.description
  # group_id - (required) is a type of string
  group_id = var.group_id
  # name - (required) is a type of string
  name = var.name
  # service_type - (required) is a type of string
  service_type = var.service_type
  # stage_names - (optional) is a type of set of string
  stage_names = var.stage_names

  dynamic "constant_parameters" {
    for_each = var.constant_parameters
    content {
      # description - (optional) is a type of string
      description = constant_parameters.value["description"]
      # in - (required) is a type of string
      in = constant_parameters.value["in"]
      # name - (required) is a type of string
      name = constant_parameters.value["name"]
      # value - (required) is a type of string
      value = constant_parameters.value["value"]
    }
  }

  dynamic "fc_service_config" {
    for_each = var.fc_service_config
    content {
      # arn_role - (optional) is a type of string
      arn_role = fc_service_config.value["arn_role"]
      # function_name - (required) is a type of string
      function_name = fc_service_config.value["function_name"]
      # region - (required) is a type of string
      region = fc_service_config.value["region"]
      # service_name - (required) is a type of string
      service_name = fc_service_config.value["service_name"]
      # timeout - (required) is a type of number
      timeout = fc_service_config.value["timeout"]
    }
  }

  dynamic "http_service_config" {
    for_each = var.http_service_config
    content {
      # address - (required) is a type of string
      address = http_service_config.value["address"]
      # aone_name - (optional) is a type of string
      aone_name = http_service_config.value["aone_name"]
      # method - (required) is a type of string
      method = http_service_config.value["method"]
      # path - (required) is a type of string
      path = http_service_config.value["path"]
      # timeout - (required) is a type of number
      timeout = http_service_config.value["timeout"]
    }
  }

  dynamic "http_vpc_service_config" {
    for_each = var.http_vpc_service_config
    content {
      # aone_name - (optional) is a type of string
      aone_name = http_vpc_service_config.value["aone_name"]
      # method - (required) is a type of string
      method = http_vpc_service_config.value["method"]
      # name - (required) is a type of string
      name = http_vpc_service_config.value["name"]
      # path - (required) is a type of string
      path = http_vpc_service_config.value["path"]
      # timeout - (required) is a type of number
      timeout = http_vpc_service_config.value["timeout"]
    }
  }

  dynamic "mock_service_config" {
    for_each = var.mock_service_config
    content {
      # aone_name - (optional) is a type of string
      aone_name = mock_service_config.value["aone_name"]
      # result - (required) is a type of string
      result = mock_service_config.value["result"]
    }
  }

  dynamic "request_config" {
    for_each = var.request_config
    content {
      # body_format - (optional) is a type of string
      body_format = request_config.value["body_format"]
      # method - (required) is a type of string
      method = request_config.value["method"]
      # mode - (required) is a type of string
      mode = request_config.value["mode"]
      # path - (required) is a type of string
      path = request_config.value["path"]
      # protocol - (required) is a type of string
      protocol = request_config.value["protocol"]
    }
  }

  dynamic "request_parameters" {
    for_each = var.request_parameters
    content {
      # default_value - (optional) is a type of string
      default_value = request_parameters.value["default_value"]
      # description - (optional) is a type of string
      description = request_parameters.value["description"]
      # in - (required) is a type of string
      in = request_parameters.value["in"]
      # in_service - (required) is a type of string
      in_service = request_parameters.value["in_service"]
      # name - (required) is a type of string
      name = request_parameters.value["name"]
      # name_service - (required) is a type of string
      name_service = request_parameters.value["name_service"]
      # required - (required) is a type of string
      required = request_parameters.value["required"]
      # type - (required) is a type of string
      type = request_parameters.value["type"]
    }
  }

  dynamic "system_parameters" {
    for_each = var.system_parameters
    content {
      # in - (required) is a type of string
      in = system_parameters.value["in"]
      # name - (required) is a type of string
      name = system_parameters.value["name"]
      # name_service - (required) is a type of string
      name_service = system_parameters.value["name_service"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_id" {
  description = "returns a string"
  value       = alicloud_api_gateway_api.this.api_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_api_gateway_api.this.id
}

output "this" {
  value = alicloud_api_gateway_api.this
}
```

[top](#index)