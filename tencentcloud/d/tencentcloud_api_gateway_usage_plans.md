# tencentcloud_api_gateway_usage_plans

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_api_gateway_usage_plans" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_usage_plans"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # usage_plan_id - (optional) is a type of string
  usage_plan_id = null
  # usage_plan_name - (optional) is a type of string
  usage_plan_name = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "usage_plan_id" {
  description = "(optional) - ID of the usage plan."
  type        = string
  default     = null
}

variable "usage_plan_name" {
  description = "(optional) - Name of the usage plan."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_usage_plans" "this" {
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # usage_plan_id - (optional) is a type of string
  usage_plan_id = var.usage_plan_id
  # usage_plan_name - (optional) is a type of string
  usage_plan_name = var.usage_plan_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_usage_plans.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_usage_plans.this.list
}

output "this" {
  value = tencentcloud_api_gateway_usage_plans.this
}
```

[top](#index)