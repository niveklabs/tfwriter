# tencentcloud_api_gateway_throttling_apis

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
module "tencentcloud_api_gateway_throttling_apis" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_throttling_apis"

  # environment_names - (optional) is a type of list of string
  environment_names = []
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # service_id - (optional) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "environment_names" {
  description = "(optional) - Environment list."
  type        = list(string)
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "service_id" {
  description = "(optional) - Unique service ID of API."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_throttling_apis" "this" {
  # environment_names - (optional) is a type of list of string
  environment_names = var.environment_names
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # service_id - (optional) is a type of string
  service_id = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_throttling_apis.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_throttling_apis.this.list
}

output "this" {
  value = tencentcloud_api_gateway_throttling_apis.this
}
```

[top](#index)