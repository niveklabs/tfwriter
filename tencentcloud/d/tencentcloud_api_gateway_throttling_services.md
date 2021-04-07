# tencentcloud_api_gateway_throttling_services

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
module "tencentcloud_api_gateway_throttling_services" {
  source = "./modules/tencentcloud/d/tencentcloud_api_gateway_throttling_services"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # service_id - (optional) is a type of string
  service_id = null
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
  description = "(optional) - Service ID for query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_api_gateway_throttling_services" "this" {
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
  value       = data.tencentcloud_api_gateway_throttling_services.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_api_gateway_throttling_services.this.list
}

output "this" {
  value = tencentcloud_api_gateway_throttling_services.this
}
```

[top](#index)