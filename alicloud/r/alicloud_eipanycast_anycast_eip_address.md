# alicloud_eipanycast_anycast_eip_address

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_eipanycast_anycast_eip_address" {
  source = "./modules/alicloud/r/alicloud_eipanycast_anycast_eip_address"

  # anycast_eip_address_name - (optional) is a type of string
  anycast_eip_address_name = null
  # bandwidth - (optional) is a type of number
  bandwidth = null
  # description - (optional) is a type of string
  description = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # service_location - (required) is a type of string
  service_location = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "anycast_eip_address_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_location" {
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
resource "alicloud_eipanycast_anycast_eip_address" "this" {
  anycast_eip_address_name = var.anycast_eip_address_name
  bandwidth                = var.bandwidth
  description              = var.description
  internet_charge_type     = var.internet_charge_type
  payment_type             = var.payment_type
  service_location         = var.service_location

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
output "bandwidth" {
  description = "returns a number"
  value       = alicloud_eipanycast_anycast_eip_address.this.bandwidth
}

output "id" {
  description = "returns a string"
  value       = alicloud_eipanycast_anycast_eip_address.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_eipanycast_anycast_eip_address.this.status
}

output "this" {
  value = alicloud_eipanycast_anycast_eip_address.this
}
```

[top](#index)