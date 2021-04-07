# alicloud_drds_instances

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
module "alicloud_drds_instances" {
  source = "./modules/alicloud/d/alicloud_drds_instances"

  # description_regex - (optional) is a type of string
  description_regex = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "description_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

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
```

[top](#index)

### Datasource

```terraform
data "alicloud_drds_instances" "this" {
  # description_regex - (optional) is a type of string
  description_regex = var.description_regex
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.alicloud_drds_instances.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_drds_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_drds_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_drds_instances.this.instances
}

output "this" {
  value = alicloud_drds_instances.this
}
```

[top](#index)