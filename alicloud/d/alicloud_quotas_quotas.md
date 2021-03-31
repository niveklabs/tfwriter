# alicloud_quotas_quotas

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
module "alicloud_quotas_quotas" {
  source = "./modules/alicloud/d/alicloud_quotas_quotas"

  # group_code - (optional) is a type of string
  group_code = null
  # key_word - (optional) is a type of string
  key_word = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # product_code - (required) is a type of string
  product_code = null
  # quota_action_code - (optional) is a type of string
  quota_action_code = null
  # quota_category - (optional) is a type of string
  quota_category = null
  # sort_field - (optional) is a type of string
  sort_field = null
  # sort_order - (optional) is a type of string
  sort_order = null

  dimensions = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_word" {
  description = "(optional)"
  type        = string
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

variable "product_code" {
  description = "(required)"
  type        = string
}

variable "quota_action_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_field" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dimensions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_quotas_quotas" "this" {
  group_code        = var.group_code
  key_word          = var.key_word
  name_regex        = var.name_regex
  output_file       = var.output_file
  product_code      = var.product_code
  quota_action_code = var.quota_action_code
  quota_category    = var.quota_category
  sort_field        = var.sort_field
  sort_order        = var.sort_order

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      key   = dimensions.value["key"]
      value = dimensions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_quotas_quotas.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_quotas_quotas.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_quotas_quotas.this.names
}

output "quotas" {
  description = "returns a list of object"
  value       = data.alicloud_quotas_quotas.this.quotas
}

output "this" {
  value = alicloud_quotas_quotas.this
}
```

[top](#index)