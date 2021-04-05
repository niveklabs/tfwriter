# alicloud_havip

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
module "alicloud_havip" {
  source = "./modules/alicloud/r/alicloud_havip"

  # description - (optional) is a type of string
  description = null
  # havip_name - (optional) is a type of string
  havip_name = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "havip_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_havip" "this" {
  description = var.description
  havip_name  = var.havip_name
  ip_address  = var.ip_address
  vswitch_id  = var.vswitch_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_havip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_havip.this.ip_address
}

output "status" {
  description = "returns a string"
  value       = alicloud_havip.this.status
}

output "this" {
  value = alicloud_havip.this
}
```

[top](#index)