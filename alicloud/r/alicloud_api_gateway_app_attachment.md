# alicloud_api_gateway_app_attachment

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_api_gateway_app_attachment" {
  source = "./modules/alicloud/r/alicloud_api_gateway_app_attachment"

  # api_id - (required) is a type of string
  api_id = null
  # app_id - (required) is a type of string
  app_id = null
  # group_id - (required) is a type of string
  group_id = null
  # stage_name - (required) is a type of string
  stage_name = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "app_id" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "stage_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_api_gateway_app_attachment" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # app_id - (required) is a type of string
  app_id = var.app_id
  # group_id - (required) is a type of string
  group_id = var.group_id
  # stage_name - (required) is a type of string
  stage_name = var.stage_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_api_gateway_app_attachment.this.id
}

output "this" {
  value = alicloud_api_gateway_app_attachment.this
}
```

[top](#index)