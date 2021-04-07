# tencentcloud_api_gateway_ip_strategy

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
module "tencentcloud_api_gateway_ip_strategy" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_ip_strategy"

  # service_id - (required) is a type of string
  service_id = null
  # strategy_data - (required) is a type of string
  strategy_data = null
  # strategy_name - (required) is a type of string
  strategy_name = null
  # strategy_type - (required) is a type of string
  strategy_type = null
}
```

[top](#index)

### Variables

```terraform
variable "service_id" {
  description = "(required) - The ID of the API gateway service."
  type        = string
}

variable "strategy_data" {
  description = "(required) - IP address data."
  type        = string
}

variable "strategy_name" {
  description = "(required) - User defined strategy name."
  type        = string
}

variable "strategy_type" {
  description = "(required) - Blacklist or whitelist."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_ip_strategy" "this" {
  service_id    = var.service_id
  strategy_data = var.strategy_data
  strategy_name = var.strategy_name
  strategy_type = var.strategy_type
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_ip_strategy.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_ip_strategy.this.id
}

output "strategy_id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_ip_strategy.this.strategy_id
}

output "this" {
  value = tencentcloud_api_gateway_ip_strategy.this
}
```

[top](#index)