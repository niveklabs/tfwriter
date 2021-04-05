# alicloud_nas_access_rules

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
module "alicloud_nas_access_rules" {
  source = "./modules/alicloud/d/alicloud_nas_access_rules"

  # access_group_name - (required) is a type of string
  access_group_name = null
  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # rw_access - (optional) is a type of string
  rw_access = null
  # source_cidr_ip - (optional) is a type of string
  source_cidr_ip = null
  # user_access - (optional) is a type of string
  user_access = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_name" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rw_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_cidr_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_access" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_nas_access_rules" "this" {
  access_group_name = var.access_group_name
  ids               = var.ids
  output_file       = var.output_file
  rw_access         = var.rw_access
  source_cidr_ip    = var.source_cidr_ip
  user_access       = var.user_access
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_nas_access_rules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_nas_access_rules.this.ids
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_nas_access_rules.this.rules
}

output "this" {
  value = alicloud_nas_access_rules.this
}
```

[top](#index)