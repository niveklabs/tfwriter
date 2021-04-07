# alicloud_quotas_application_infos

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
module "alicloud_quotas_application_infos" {
  source = "./modules/alicloud/d/alicloud_quotas_application_infos"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # key_word - (optional) is a type of string
  key_word = null
  # output_file - (optional) is a type of string
  output_file = null
  # product_code - (required) is a type of string
  product_code = null
  # quota_action_code - (optional) is a type of string
  quota_action_code = null
  # quota_category - (optional) is a type of string
  quota_category = null
  # status - (optional) is a type of string
  status = null

  dimensions = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key_word" {
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

variable "status" {
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
data "alicloud_quotas_application_infos" "this" {
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # ids - (optional) is a type of list of string
  ids = var.ids
  # key_word - (optional) is a type of string
  key_word = var.key_word
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # product_code - (required) is a type of string
  product_code = var.product_code
  # quota_action_code - (optional) is a type of string
  quota_action_code = var.quota_action_code
  # quota_category - (optional) is a type of string
  quota_category = var.quota_category
  # status - (optional) is a type of string
  status = var.status

  dynamic "dimensions" {
    for_each = var.dimensions
    content {
      # key - (optional) is a type of string
      key = dimensions.value["key"]
      # value - (optional) is a type of string
      value = dimensions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "applications" {
  description = "returns a list of object"
  value       = data.alicloud_quotas_application_infos.this.applications
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_quotas_application_infos.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_quotas_application_infos.this.ids
}

output "this" {
  value = alicloud_quotas_application_infos.this
}
```

[top](#index)