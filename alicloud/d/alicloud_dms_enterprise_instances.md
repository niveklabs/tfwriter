# alicloud_dms_enterprise_instances

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
module "alicloud_dms_enterprise_instances" {
  source = "./modules/alicloud/d/alicloud_dms_enterprise_instances"

  # env_type - (optional) is a type of string
  env_type = null
  # instance_alias_regex - (optional) is a type of string
  instance_alias_regex = null
  # instance_source - (optional) is a type of string
  instance_source = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # net_type - (optional) is a type of string
  net_type = null
  # output_file - (optional) is a type of string
  output_file = null
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
variable "env_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_alias_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "net_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
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
data "alicloud_dms_enterprise_instances" "this" {
  # env_type - (optional) is a type of string
  env_type = var.env_type
  # instance_alias_regex - (optional) is a type of string
  instance_alias_regex = var.instance_alias_regex
  # instance_source - (optional) is a type of string
  instance_source = var.instance_source
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # net_type - (optional) is a type of string
  net_type = var.net_type
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # search_key - (optional) is a type of string
  search_key = var.search_key
  # status - (optional) is a type of string
  status = var.status
  # tid - (optional) is a type of number
  tid = var.tid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_dms_enterprise_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_dms_enterprise_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_dms_enterprise_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_dms_enterprise_instances.this.names
}

output "this" {
  value = alicloud_dms_enterprise_instances.this
}
```

[top](#index)