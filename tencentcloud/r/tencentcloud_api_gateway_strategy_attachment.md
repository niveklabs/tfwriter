# tencentcloud_api_gateway_strategy_attachment

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
module "tencentcloud_api_gateway_strategy_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_strategy_attachment"

  # bind_api_id - (required) is a type of string
  bind_api_id = null
  # environment_name - (required) is a type of string
  environment_name = null
  # service_id - (required) is a type of string
  service_id = null
  # strategy_id - (required) is a type of string
  strategy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bind_api_id" {
  description = "(required) - The API that needs to be bound."
  type        = string
}

variable "environment_name" {
  description = "(required) - The environment of the strategy association. Valid values: `test`, `release`, `prepub`."
  type        = string
}

variable "service_id" {
  description = "(required) - The ID of the API gateway service."
  type        = string
}

variable "strategy_id" {
  description = "(required) - The ID of the API gateway strategy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_strategy_attachment" "this" {
  bind_api_id      = var.bind_api_id
  environment_name = var.environment_name
  service_id       = var.service_id
  strategy_id      = var.strategy_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_strategy_attachment.this.id
}

output "this" {
  value = tencentcloud_api_gateway_strategy_attachment.this
}
```

[top](#index)