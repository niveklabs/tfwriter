# alicloud_yundun_dbaudit_instance

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_yundun_dbaudit_instance" {
  source = "./modules/alicloud/r/alicloud_yundun_dbaudit_instance"

  # description - (required) is a type of string
  description = null
  # period - (optional) is a type of number
  period = null
  # plan_code - (required) is a type of string
  plan_code = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (required) is a type of string
  vswitch_id = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "plan_code" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_yundun_dbaudit_instance" "this" {
  description       = var.description
  period            = var.period
  plan_code         = var.plan_code
  resource_group_id = var.resource_group_id
  tags              = var.tags
  vswitch_id        = var.vswitch_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_yundun_dbaudit_instance.this.id
}

output "this" {
  value = alicloud_yundun_dbaudit_instance.this
}
```

[top](#index)