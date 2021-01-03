# alicloud_hbase_instance_types

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
module "alicloud_hbase_instance_types" {
  source = "./modules/alicloud/d/alicloud_hbase_instance_types"

  # instance_type - (optional) is a type of string
  instance_type = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_type" {
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
data "alicloud_hbase_instance_types" "this" {
  instance_type = var.instance_type
  output_file   = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_hbase_instance_types.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_hbase_instance_types.this.ids
}

output "types" {
  description = "returns a list of object"
  value       = data.alicloud_hbase_instance_types.this.types
}

output "this" {
  value = alicloud_hbase_instance_types.this
}
```

[top](#index)