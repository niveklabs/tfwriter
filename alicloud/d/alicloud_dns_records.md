# alicloud_dns_records

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dns_records" {
  source = "./modules/alicloud/d/alicloud_dns_records"

  # domain_name - (required) is a type of string
  domain_name = null
  # host_record_regex - (optional) is a type of string
  host_record_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # is_locked - (optional) is a type of bool
  is_locked = null
  # line - (optional) is a type of string
  line = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # value_regex - (optional) is a type of string
  value_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "host_record_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "is_locked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "line" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
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

variable "value_regex" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_dns_records" "this" {
  domain_name       = var.domain_name
  host_record_regex = var.host_record_regex
  ids               = var.ids
  is_locked         = var.is_locked
  line              = var.line
  output_file       = var.output_file
  status            = var.status
  type              = var.type
  value_regex       = var.value_regex
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_dns_records.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_dns_records.this.ids
}

output "records" {
  description = "returns a list of object"
  value       = data.alicloud_dns_records.this.records
}

output "urls" {
  description = "returns a list of string"
  value       = data.alicloud_dns_records.this.urls
}

output "this" {
  value = alicloud_dns_records.this
}
```

[top](#index)