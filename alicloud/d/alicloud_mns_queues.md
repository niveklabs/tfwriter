# alicloud_mns_queues

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
module "alicloud_mns_queues" {
  source = "./modules/alicloud/d/alicloud_mns_queues"

  # name_prefix - (optional) is a type of string
  name_prefix = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name_prefix" {
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
data "alicloud_mns_queues" "this" {
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_mns_queues.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_mns_queues.this.names
}

output "queues" {
  description = "returns a list of object"
  value       = data.alicloud_mns_queues.this.queues
}

output "this" {
  value = alicloud_mns_queues.this
}
```

[top](#index)