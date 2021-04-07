# tencentcloud_api_gateway_api_keys

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
module "tencentcloud_api_gateway_api_keys" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_api_keys"

  # api_key_id - (optional) is a type of string
  api_key_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # secret_name - (optional) is a type of string
  secret_name = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key_id" {
  description = "(optional) - Created API key ID, this field is exactly the same as ID."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(optional) - Custom key name."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_api_keys" "this" {
  # api_key_id - (optional) is a type of string
  api_key_id = var.api_key_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # secret_name - (optional) is a type of string
  secret_name = var.secret_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_api_keys.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_api_keys.this.list
}

output "this" {
  value = tencentcloud_api_gateway_api_keys.this
}
```

[top](#index)