# tencentcloud_api_gateway_usage_plan_attachment

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
module "tencentcloud_api_gateway_usage_plan_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_usage_plan_attachment"

  # api_id - (optional) is a type of string
  api_id = null
  # bind_type - (optional) is a type of string
  bind_type = null
  # environment - (required) is a type of string
  environment = null
  # service_id - (required) is a type of string
  service_id = null
  # usage_plan_id - (required) is a type of string
  usage_plan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(optional) - ID of the API. This parameter will be required when `bind_type` is `API`."
  type        = string
  default     = null
}

variable "bind_type" {
  description = "(optional) - Binding type. Valid values: `API`, `SERVICE`. Default value is `SERVICE`."
  type        = string
  default     = null
}

variable "environment" {
  description = "(required) - The environment to be bound. Valid values: `test`, `prepub`, `release`."
  type        = string
}

variable "service_id" {
  description = "(required) - ID of the service."
  type        = string
}

variable "usage_plan_id" {
  description = "(required) - ID of the usage plan."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_usage_plan_attachment" "this" {
  # api_id - (optional) is a type of string
  api_id = var.api_id
  # bind_type - (optional) is a type of string
  bind_type = var.bind_type
  # environment - (required) is a type of string
  environment = var.environment
  # service_id - (required) is a type of string
  service_id = var.service_id
  # usage_plan_id - (required) is a type of string
  usage_plan_id = var.usage_plan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_usage_plan_attachment.this.id
}

output "this" {
  value = tencentcloud_api_gateway_usage_plan_attachment.this
}
```

[top](#index)