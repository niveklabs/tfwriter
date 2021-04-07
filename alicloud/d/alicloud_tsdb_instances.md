# alicloud_tsdb_instances

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
module "alicloud_tsdb_instances" {
  source = "./modules/alicloud/d/alicloud_tsdb_instances"

  # app_key - (optional) is a type of string
  app_key = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # engine_type - (optional) is a type of string
  engine_type = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # query_str - (optional) is a type of string
  query_str = null
  # status - (optional) is a type of string
  status = null
  # status_list - (optional) is a type of string
  status_list = null
}
```

[top](#index)

### Variables

```terraform
variable "app_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "engine_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_str" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status_list" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_tsdb_instances" "this" {
  # app_key - (optional) is a type of string
  app_key = var.app_key
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # engine_type - (optional) is a type of string
  engine_type = var.engine_type
  # ids - (optional) is a type of list of string
  ids = var.ids
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # query_str - (optional) is a type of string
  query_str = var.query_str
  # status - (optional) is a type of string
  status = var.status
  # status_list - (optional) is a type of string
  status_list = var.status_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_tsdb_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_tsdb_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_tsdb_instances.this.instances
}

output "this" {
  value = alicloud_tsdb_instances.this
}
```

[top](#index)