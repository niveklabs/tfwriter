# alicloud_pvtz_zone_records

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
module "alicloud_pvtz_zone_records" {
  source = "./modules/alicloud/d/alicloud_pvtz_zone_records"

  # ids - (optional) is a type of list of string
  ids = []
  # keyword - (optional) is a type of string
  keyword = null
  # lang - (optional) is a type of string
  lang = null
  # output_file - (optional) is a type of string
  output_file = null
  # search_mode - (optional) is a type of string
  search_mode = null
  # status - (optional) is a type of string
  status = null
  # tag - (optional) is a type of string
  tag = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
  # zone_id - (required) is a type of string
  zone_id = null
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

variable "keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
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

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_pvtz_zone_records" "this" {
  ids            = var.ids
  keyword        = var.keyword
  lang           = var.lang
  output_file    = var.output_file
  search_mode    = var.search_mode
  status         = var.status
  tag            = var.tag
  user_client_ip = var.user_client_ip
  zone_id        = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_pvtz_zone_records.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_pvtz_zone_records.this.ids
}

output "records" {
  description = "returns a list of object"
  value       = data.alicloud_pvtz_zone_records.this.records
}

output "this" {
  value = alicloud_pvtz_zone_records.this
}
```

[top](#index)