# alicloud_mongodb_instances

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
module "alicloud_mongodb_instances" {
  source = "./modules/alicloud/d/alicloud_mongodb_instances"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_class - (optional) is a type of string
  instance_class = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_mongodb_instances" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # ids - (optional) is a type of list of string
  ids = var.ids
  # instance_class - (optional) is a type of string
  instance_class = var.instance_class
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_mongodb_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_mongodb_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_mongodb_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_mongodb_instances.this.names
}

output "this" {
  value = alicloud_mongodb_instances.this
}
```

[top](#index)