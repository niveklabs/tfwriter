# alicloud_pvtz_zone_attachment

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
module "alicloud_pvtz_zone_attachment" {
  source = "./modules/alicloud/r/alicloud_pvtz_zone_attachment"

  # lang - (optional) is a type of string
  lang = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
  # vpc_ids - (optional) is a type of set of string
  vpc_ids = []
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vpcs = [{
    region_id = null
    vpc_id    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "vpcs" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      region_id = string
      vpc_id    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_pvtz_zone_attachment" "this" {
  lang           = var.lang
  user_client_ip = var.user_client_ip
  vpc_ids        = var.vpc_ids
  zone_id        = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "vpcs" {
    for_each = var.vpcs
    content {
      region_id = vpcs.value["region_id"]
      vpc_id    = vpcs.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_pvtz_zone_attachment.this.id
}

output "vpc_ids" {
  description = "returns a set of string"
  value       = alicloud_pvtz_zone_attachment.this.vpc_ids
}

output "this" {
  value = alicloud_pvtz_zone_attachment.this
}
```

[top](#index)