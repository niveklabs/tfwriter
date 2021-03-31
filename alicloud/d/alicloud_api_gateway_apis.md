# alicloud_api_gateway_apis

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_api_gateway_apis" {
  source = "./modules/alicloud/d/alicloud_api_gateway_apis"

  # api_id - (optional) is a type of string
  api_id = null
  # group_id - (optional) is a type of string
  group_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_api_gateway_apis" "this" {
  api_id      = var.api_id
  group_id    = var.group_id
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "apis" {
  description = "returns a list of object"
  value       = data.alicloud_api_gateway_apis.this.apis
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_api_gateway_apis.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_api_gateway_apis.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_api_gateway_apis.this.names
}

output "this" {
  value = alicloud_api_gateway_apis.this
}
```

[top](#index)