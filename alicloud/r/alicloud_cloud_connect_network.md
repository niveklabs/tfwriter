# alicloud_cloud_connect_network

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_cloud_connect_network" {
  source = "./modules/alicloud/r/alicloud_cloud_connect_network"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # is_default - (required) is a type of bool
  is_default = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cloud_connect_network" "this" {
  # cidr_block - (optional) is a type of string
  cidr_block = var.cidr_block
  # description - (optional) is a type of string
  description = var.description
  # is_default - (required) is a type of bool
  is_default = var.is_default
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cloud_connect_network.this.id
}

output "this" {
  value = alicloud_cloud_connect_network.this
}
```

[top](#index)