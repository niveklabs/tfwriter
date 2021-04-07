# tencentcloud_api_gateway_api_key

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
module "tencentcloud_api_gateway_api_key" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_api_key"

  # secret_name - (required) is a type of string
  secret_name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "secret_name" {
  description = "(required) - Custom key name."
  type        = string
}

variable "status" {
  description = "(optional) - Key status. Valid values: `on`, `off`."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_api_key" "this" {
  # secret_name - (required) is a type of string
  secret_name = var.secret_name
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "access_key_secret" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api_key.this.access_key_secret
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api_key.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api_key.this.id
}

output "modify_time" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api_key.this.modify_time
}

output "this" {
  value = tencentcloud_api_gateway_api_key.this
}
```

[top](#index)