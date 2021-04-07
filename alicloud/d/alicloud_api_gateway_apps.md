# alicloud_api_gateway_apps

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_api_gateway_apps" {
  source = "./modules/alicloud/d/alicloud_api_gateway_apps"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_api_gateway_apps" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "apps" {
  description = "returns a list of object"
  value       = data.alicloud_api_gateway_apps.this.apps
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_api_gateway_apps.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_api_gateway_apps.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_api_gateway_apps.this.names
}

output "this" {
  value = alicloud_api_gateway_apps.this
}
```

[top](#index)