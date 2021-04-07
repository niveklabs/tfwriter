# tencentcloud_api_gateway_apis

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
module "tencentcloud_api_gateway_apis" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_apis"

  # api_id - (optional) is a type of string
  api_id = null
  # api_name - (optional) is a type of string
  api_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # service_id - (required) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(optional) - Created API ID."
  type        = string
  default     = null
}

variable "api_name" {
  description = "(optional) - Custom API name."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required) - Service ID for query."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_apis" "this" {
  # api_id - (optional) is a type of string
  api_id = var.api_id
  # api_name - (optional) is a type of string
  api_name = var.api_name
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # service_id - (required) is a type of string
  service_id = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_api_gateway_apis.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_apis.this.list
}

output "this" {
  value = tencentcloud_api_gateway_apis.this
}
```

[top](#index)