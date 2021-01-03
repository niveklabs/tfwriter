# alicloud_router_interfaces

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
module "alicloud_router_interfaces" {
  source = "./modules/alicloud/d/alicloud_router_interfaces"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # opposite_interface_id - (optional) is a type of string
  opposite_interface_id = null
  # opposite_interface_owner_id - (optional) is a type of string
  opposite_interface_owner_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # role - (optional) is a type of string
  role = null
  # router_id - (optional) is a type of string
  router_id = null
  # router_type - (optional) is a type of string
  router_type = null
  # specification - (optional) is a type of string
  specification = null
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

variable "opposite_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "opposite_interface_owner_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "router_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "specification" {
  description = "(optional)"
  type        = string
  default     = null
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
data "alicloud_router_interfaces" "this" {
  ids                         = var.ids
  name_regex                  = var.name_regex
  opposite_interface_id       = var.opposite_interface_id
  opposite_interface_owner_id = var.opposite_interface_owner_id
  output_file                 = var.output_file
  role                        = var.role
  router_id                   = var.router_id
  router_type                 = var.router_type
  specification               = var.specification
  status                      = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_router_interfaces.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_router_interfaces.this.ids
}

output "interfaces" {
  description = "returns a list of object"
  value       = data.alicloud_router_interfaces.this.interfaces
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_router_interfaces.this.names
}

output "this" {
  value = alicloud_router_interfaces.this
}
```

[top](#index)