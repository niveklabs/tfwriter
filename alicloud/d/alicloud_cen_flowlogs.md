# alicloud_cen_flowlogs

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
module "alicloud_cen_flowlogs" {
  source = "./modules/alicloud/d/alicloud_cen_flowlogs"

  # cen_id - (optional) is a type of string
  cen_id = null
  # description - (optional) is a type of string
  description = null
  # ids - (optional) is a type of list of string
  ids = []
  # log_store_name - (optional) is a type of string
  log_store_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # project_name - (optional) is a type of string
  project_name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "log_store_name" {
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

variable "project_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cen_flowlogs" "this" {
  cen_id         = var.cen_id
  description    = var.description
  ids            = var.ids
  log_store_name = var.log_store_name
  name_regex     = var.name_regex
  output_file    = var.output_file
  project_name   = var.project_name
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "flowlogs" {
  description = "returns a list of object"
  value       = data.alicloud_cen_flowlogs.this.flowlogs
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_flowlogs.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cen_flowlogs.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cen_flowlogs.this.names
}

output "this" {
  value = alicloud_cen_flowlogs.this
}
```

[top](#index)