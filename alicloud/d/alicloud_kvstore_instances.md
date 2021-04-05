# alicloud_kvstore_instances

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
module "alicloud_kvstore_instances" {
  source = "./modules/alicloud/d/alicloud_kvstore_instances"

  # architecture_type - (optional) is a type of string
  architecture_type = null
  # edition_type - (optional) is a type of string
  edition_type = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # expired - (optional) is a type of string
  expired = null
  # global_instance - (optional) is a type of bool
  global_instance = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_class - (optional) is a type of string
  instance_class = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # network_type - (optional) is a type of string
  network_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # search_key - (optional) is a type of string
  search_key = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "architecture_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expired" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global_instance" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_class" {
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

variable "network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kvstore_instances" "this" {
  architecture_type = var.architecture_type
  edition_type      = var.edition_type
  enable_details    = var.enable_details
  engine_version    = var.engine_version
  expired           = var.expired
  global_instance   = var.global_instance
  ids               = var.ids
  instance_class    = var.instance_class
  instance_type     = var.instance_type
  name_regex        = var.name_regex
  network_type      = var.network_type
  output_file       = var.output_file
  payment_type      = var.payment_type
  resource_group_id = var.resource_group_id
  search_key        = var.search_key
  status            = var.status
  tags              = var.tags
  vpc_id            = var.vpc_id
  vswitch_id        = var.vswitch_id
  zone_id           = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kvstore_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_kvstore_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_kvstore_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_kvstore_instances.this.names
}

output "this" {
  value = alicloud_kvstore_instances.this
}
```

[top](#index)