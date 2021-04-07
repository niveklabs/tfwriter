# alicloud_waf_instances

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
module "alicloud_waf_instances" {
  source = "./modules/alicloud/d/alicloud_waf_instances"

  # ids - (optional) is a type of list of string
  ids = []
  # instance_source - (optional) is a type of string
  instance_source = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # status - (optional) is a type of number
  status = null
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

variable "instance_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
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
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_waf_instances" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # instance_source - (optional) is a type of string
  instance_source = var.instance_source
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # status - (optional) is a type of number
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_waf_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_waf_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_waf_instances.this.instances
}

output "this" {
  value = alicloud_waf_instances.this
}
```

[top](#index)