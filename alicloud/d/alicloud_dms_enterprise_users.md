# alicloud_dms_enterprise_users

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
module "alicloud_dms_enterprise_users" {
  source = "./modules/alicloud/d/alicloud_dms_enterprise_users"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # role - (optional) is a type of string
  role = null
  # search_key - (optional) is a type of string
  search_key = null
  # status - (optional) is a type of string
  status = null
  # tid - (optional) is a type of number
  tid = null
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

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_dms_enterprise_users" "this" {
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
  role        = var.role
  search_key  = var.search_key
  status      = var.status
  tid         = var.tid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_dms_enterprise_users.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_dms_enterprise_users.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_dms_enterprise_users.this.names
}

output "users" {
  description = "returns a list of object"
  value       = data.alicloud_dms_enterprise_users.this.users
}

output "this" {
  value = alicloud_dms_enterprise_users.this
}
```

[top](#index)