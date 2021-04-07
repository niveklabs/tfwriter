# tencentcloud_api_gateway_ip_strategies

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
module "tencentcloud_api_gateway_ip_strategies" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_ip_strategies"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # service_id - (required) is a type of string
  service_id = null
  # strategy_name - (optional) is a type of string
  strategy_name = null
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

variable "service_id" {
  description = "(required) - The service ID to be queried."
  type        = string
}

variable "strategy_name" {
  description = "(optional) - Name of IP policy."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_ip_strategies" "this" {
  result_output_file = var.result_output_file
  service_id         = var.service_id
  strategy_name      = var.strategy_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_ip_strategies.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_ip_strategies.this.list
}

output "this" {
  value = tencentcloud_api_gateway_ip_strategies.this
}
```

[top](#index)