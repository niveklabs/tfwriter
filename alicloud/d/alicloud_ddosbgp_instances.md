# alicloud_ddosbgp_instances

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
module "alicloud_ddosbgp_instances" {
  source = "./modules/alicloud/d/alicloud_ddosbgp_instances"

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
data "alicloud_ddosbgp_instances" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.alicloud_ddosbgp_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ddosbgp_instances.this.ids
}

output "instances" {
  description = "returns a list of object"
  value       = data.alicloud_ddosbgp_instances.this.instances
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ddosbgp_instances.this.names
}

output "this" {
  value = alicloud_ddosbgp_instances.this
}
```

[top](#index)