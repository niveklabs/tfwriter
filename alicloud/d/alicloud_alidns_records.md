# alicloud_alidns_records

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
module "alicloud_alidns_records" {
  source = "./modules/alicloud/d/alicloud_alidns_records"

  # direction - (optional) is a type of string
  direction = null
  # domain_name - (required) is a type of string
  domain_name = null
  # group_id - (optional) is a type of number
  group_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # key_word - (optional) is a type of string
  key_word = null
  # lang - (optional) is a type of string
  lang = null
  # line - (optional) is a type of string
  line = null
  # order_by - (optional) is a type of string
  order_by = null
  # output_file - (optional) is a type of string
  output_file = null
  # rr_key_word - (optional) is a type of string
  rr_key_word = null
  # rr_regex - (optional) is a type of string
  rr_regex = null
  # search_mode - (optional) is a type of string
  search_mode = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # type_key_word - (optional) is a type of string
  type_key_word = null
  # value_key_word - (optional) is a type of string
  value_key_word = null
  # value_regex - (optional) is a type of string
  value_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(optional)"
  type        = number
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

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "line" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rr_key_word" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rr_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_key_word" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value_key_word" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value_regex" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_alidns_records" "this" {
  # direction - (optional) is a type of string
  direction = var.direction
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # group_id - (optional) is a type of number
  group_id = var.group_id
  # ids - (optional) is a type of list of string
  ids = var.ids
  # key_word - (optional) is a type of string
  key_word = var.key_word
  # lang - (optional) is a type of string
  lang = var.lang
  # line - (optional) is a type of string
  line = var.line
  # order_by - (optional) is a type of string
  order_by = var.order_by
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # rr_key_word - (optional) is a type of string
  rr_key_word = var.rr_key_word
  # rr_regex - (optional) is a type of string
  rr_regex = var.rr_regex
  # search_mode - (optional) is a type of string
  search_mode = var.search_mode
  # status - (optional) is a type of string
  status = var.status
  # type - (optional) is a type of string
  type = var.type
  # type_key_word - (optional) is a type of string
  type_key_word = var.type_key_word
  # value_key_word - (optional) is a type of string
  value_key_word = var.value_key_word
  # value_regex - (optional) is a type of string
  value_regex = var.value_regex
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_alidns_records.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_alidns_records.this.ids
}

output "records" {
  description = "returns a list of object"
  value       = data.alicloud_alidns_records.this.records
}

output "this" {
  value = alicloud_alidns_records.this
}
```

[top](#index)