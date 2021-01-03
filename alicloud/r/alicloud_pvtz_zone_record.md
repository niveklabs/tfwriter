# alicloud_pvtz_zone_record

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
module "alicloud_pvtz_zone_record" {
  source = "./modules/alicloud/r/alicloud_pvtz_zone_record"

  # lang - (optional) is a type of string
  lang = null
  # priority - (optional) is a type of number
  priority = null
  # remark - (optional) is a type of string
  remark = null
  # resource_record - (optional) is a type of string
  resource_record = null
  # rr - (optional) is a type of string
  rr = null
  # status - (optional) is a type of string
  status = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
  # value - (required) is a type of string
  value = null
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_record" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_pvtz_zone_record" "this" {
  lang            = var.lang
  priority        = var.priority
  remark          = var.remark
  resource_record = var.resource_record
  rr              = var.rr
  status          = var.status
  ttl             = var.ttl
  type            = var.type
  user_client_ip  = var.user_client_ip
  value           = var.value
  zone_id         = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = alicloud_pvtz_zone_record.this.id
}

output "record_id" {
  description = "returns a number"
  value       = alicloud_pvtz_zone_record.this.record_id
}

output "resource_record" {
  description = "returns a string"
  value       = alicloud_pvtz_zone_record.this.resource_record
}

output "rr" {
  description = "returns a string"
  value       = alicloud_pvtz_zone_record.this.rr
}

output "this" {
  value = alicloud_pvtz_zone_record.this
}
```

[top](#index)