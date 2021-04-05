# alicloud_vswitch

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
module "alicloud_vswitch" {
  source = "./modules/alicloud/r/alicloud_vswitch"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
  # vswitch_name - (optional) is a type of string
  vswitch_name = null
  # zone_id - (optional) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_vswitch" "this" {
  availability_zone = var.availability_zone
  cidr_block        = var.cidr_block
  description       = var.description
  name              = var.name
  tags              = var.tags
  vpc_id            = var.vpc_id
  vswitch_name      = var.vswitch_name
  zone_id           = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = alicloud_vswitch.this.availability_zone
}

output "id" {
  description = "returns a string"
  value       = alicloud_vswitch.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_vswitch.this.name
}

output "status" {
  description = "returns a string"
  value       = alicloud_vswitch.this.status
}

output "vswitch_name" {
  description = "returns a string"
  value       = alicloud_vswitch.this.vswitch_name
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_vswitch.this.zone_id
}

output "this" {
  value = alicloud_vswitch.this
}
```

[top](#index)