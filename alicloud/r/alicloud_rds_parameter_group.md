# alicloud_rds_parameter_group

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
module "alicloud_rds_parameter_group" {
  source = "./modules/alicloud/r/alicloud_rds_parameter_group"

  # engine - (required) is a type of string
  engine = null
  # engine_version - (required) is a type of string
  engine_version = null
  # parameter_group_desc - (optional) is a type of string
  parameter_group_desc = null
  # parameter_group_name - (required) is a type of string
  parameter_group_name = null

  param_detail = [{
    param_name  = null
    param_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "engine" {
  description = "(required)"
  type        = string
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "parameter_group_desc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter_group_name" {
  description = "(required)"
  type        = string
}

variable "param_detail" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      param_name  = string
      param_value = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_rds_parameter_group" "this" {
  engine               = var.engine
  engine_version       = var.engine_version
  parameter_group_desc = var.parameter_group_desc
  parameter_group_name = var.parameter_group_name

  dynamic "param_detail" {
    for_each = var.param_detail
    content {
      param_name  = param_detail.value["param_name"]
      param_value = param_detail.value["param_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_rds_parameter_group.this.id
}

output "this" {
  value = alicloud_rds_parameter_group.this
}
```

[top](#index)