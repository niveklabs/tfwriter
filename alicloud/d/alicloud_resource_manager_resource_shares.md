# alicloud_resource_manager_resource_shares

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
module "alicloud_resource_manager_resource_shares" {
  source = "./modules/alicloud/d/alicloud_resource_manager_resource_shares"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_share_name - (optional) is a type of string
  resource_share_name = null
  # resource_share_owner - (required) is a type of string
  resource_share_owner = null
  # status - (optional) is a type of string
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

variable "resource_share_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_share_owner" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_resource_shares" "this" {
  ids                  = var.ids
  name_regex           = var.name_regex
  output_file          = var.output_file
  resource_share_name  = var.resource_share_name
  resource_share_owner = var.resource_share_owner
  status               = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_resource_shares.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_resource_shares.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_resource_shares.this.names
}

output "shares" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_resource_shares.this.shares
}

output "this" {
  value = alicloud_resource_manager_resource_shares.this
}
```

[top](#index)