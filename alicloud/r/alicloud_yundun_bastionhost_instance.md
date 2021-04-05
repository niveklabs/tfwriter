# alicloud_yundun_bastionhost_instance

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
module "alicloud_yundun_bastionhost_instance" {
  source = "./modules/alicloud/r/alicloud_yundun_bastionhost_instance"

  # description - (required) is a type of string
  description = null
  # license_code - (required) is a type of string
  license_code = null
  # period - (optional) is a type of number
  period = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_ids - (required) is a type of list of string
  security_group_ids = []
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

variable "license_code" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(required)"
  type        = list(string)
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
resource "alicloud_yundun_bastionhost_instance" "this" {
  description        = var.description
  license_code       = var.license_code
  period             = var.period
  resource_group_id  = var.resource_group_id
  security_group_ids = var.security_group_ids
  tags               = var.tags
  vswitch_id         = var.vswitch_id

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
  value       = alicloud_yundun_bastionhost_instance.this.id
}

output "this" {
  value = alicloud_yundun_bastionhost_instance.this
}
```

[top](#index)