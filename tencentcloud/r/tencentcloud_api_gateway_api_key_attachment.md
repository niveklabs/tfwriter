# tencentcloud_api_gateway_api_key_attachment

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
module "tencentcloud_api_gateway_api_key_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_api_key_attachment"

  # api_key_id - (required) is a type of string
  api_key_id = null
  # usage_plan_id - (required) is a type of string
  usage_plan_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key_id" {
  description = "(required) - ID of API key."
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
resource "tencentcloud_api_gateway_api_key_attachment" "this" {
  # api_key_id - (required) is a type of string
  api_key_id = var.api_key_id
  # usage_plan_id - (required) is a type of string
  usage_plan_id = var.usage_plan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_api_key_attachment.this.id
}

output "this" {
  value = tencentcloud_api_gateway_api_key_attachment.this
}
```

[top](#index)