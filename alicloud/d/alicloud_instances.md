# alicloud_instances

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
module "alicloud_instances" {
  source = "./modules/alicloud/d/alicloud_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # ids - (optional) is a type of list of string
  ids = []
  # image_id - (optional) is a type of string
  image_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "image_id" {
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

variable "ram_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_instances" "this" {
  availability_zone = var.availability_zone
  ids               = var.ids
  image_id          = var.image_id
  name_regex        = var.name_regex
  output_file       = var.output_file
  ram_role_name     = var.ram_role_name
  resource_group_id = var.resource_group_id
  status            = var.status
  tags              = var.tags
  vpc_id            = var.vpc_id
  vswitch_id        = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_instances.this.names
}

output "this" {
  value = alicloud_instances.this
}
```

[top](#index)