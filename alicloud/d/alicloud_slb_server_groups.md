# alicloud_slb_server_groups

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
module "alicloud_slb_server_groups" {
  source = "./modules/alicloud/d/alicloud_slb_server_groups"

  # ids - (optional) is a type of list of string
  ids = []
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
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

variable "load_balancer_id" {
  description = "(required)"
  type        = string
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
data "alicloud_slb_server_groups" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id
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
  value       = data.alicloud_slb_server_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_slb_server_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_slb_server_groups.this.names
}

output "slb_server_groups" {
  description = "returns a list of object"
  value       = data.alicloud_slb_server_groups.this.slb_server_groups
}

output "this" {
  value = alicloud_slb_server_groups.this
}
```

[top](#index)