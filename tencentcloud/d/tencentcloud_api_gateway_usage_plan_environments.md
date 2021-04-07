# tencentcloud_api_gateway_usage_plan_environments

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
module "tencentcloud_api_gateway_usage_plan_environments" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_usage_plan_environments"

  # bind_type - (optional) is a type of string
  bind_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # usage_plan_id - (required) is a type of string
  usage_plan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bind_type" {
  description = "(optional) - Binding type. Valid values: `API`, `SERVICE`. Default value: `SERVICE`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "usage_plan_id" {
  description = "(required) - ID of the usage plan to be queried."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_usage_plan_environments" "this" {
  # bind_type - (optional) is a type of string
  bind_type = var.bind_type
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # usage_plan_id - (required) is a type of string
  usage_plan_id = var.usage_plan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_usage_plan_environments.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_usage_plan_environments.this.list
}

output "this" {
  value = tencentcloud_api_gateway_usage_plan_environments.this
}
```

[top](#index)