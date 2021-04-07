# alicloud_config_delivery_channels

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
module "alicloud_config_delivery_channels" {
  source = "./modules/alicloud/d/alicloud_config_delivery_channels"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
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

variable "status" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_config_delivery_channels" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # status - (optional) is a type of number
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "channels" {
  description = "returns a list of object"
  value       = data.alicloud_config_delivery_channels.this.channels
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_config_delivery_channels.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_config_delivery_channels.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_config_delivery_channels.this.names
}

output "this" {
  value = alicloud_config_delivery_channels.this
}
```

[top](#index)