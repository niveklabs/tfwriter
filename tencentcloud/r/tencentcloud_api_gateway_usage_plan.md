# tencentcloud_api_gateway_usage_plan

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
module "tencentcloud_api_gateway_usage_plan" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_usage_plan"

  # max_request_num - (optional) is a type of number
  max_request_num = null
  # max_request_num_pre_sec - (optional) is a type of number
  max_request_num_pre_sec = null
  # usage_plan_desc - (optional) is a type of string
  usage_plan_desc = null
  # usage_plan_name - (required) is a type of string
  usage_plan_name = null
}
```

[top](#index)

### Variables

```terraform
variable "max_request_num" {
  description = "(optional) - Total number of requests allowed. Valid values: -1, [1,99999999]. The default value is -1, which indicates no limit."
  type        = number
  default     = null
}

variable "max_request_num_pre_sec" {
  description = "(optional) - Limit of requests per second. Valid values: -1, [1,2000]. The default value is -1, which indicates no limit."
  type        = number
  default     = null
}

variable "usage_plan_desc" {
  description = "(optional) - Custom usage plan description."
  type        = string
  default     = null
}

variable "usage_plan_name" {
  description = "(required) - Custom usage plan name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_usage_plan" "this" {
  # max_request_num - (optional) is a type of number
  max_request_num = var.max_request_num
  # max_request_num_pre_sec - (optional) is a type of number
  max_request_num_pre_sec = var.max_request_num_pre_sec
  # usage_plan_desc - (optional) is a type of string
  usage_plan_desc = var.usage_plan_desc
  # usage_plan_name - (required) is a type of string
  usage_plan_name = var.usage_plan_name
}
```

[top](#index)

### Outputs

```terraform
output "attach_api_keys" {
  description = "returns a list of string"
  value       = tencentcloud_api_gateway_usage_plan.this.attach_api_keys
}

output "attach_list" {
  description = "returns a list of object"
  value       = tencentcloud_api_gateway_usage_plan.this.attach_list
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_usage_plan.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_usage_plan.this.id
}

output "modify_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_usage_plan.this.modify_time
}

output "this" {
  value = tencentcloud_api_gateway_usage_plan.this
}
```

[top](#index)