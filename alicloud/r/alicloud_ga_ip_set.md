# alicloud_ga_ip_set

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
module "alicloud_ga_ip_set" {
  source = "./modules/alicloud/r/alicloud_ga_ip_set"

  # accelerate_region_id - (required) is a type of string
  accelerate_region_id = null
  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # bandwidth - (optional) is a type of number
  bandwidth = null
  # ip_version - (optional) is a type of string
  ip_version = null

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
variable "accelerate_region_id" {
  description = "(required)"
  type        = string
}

variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_version" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ga_ip_set" "this" {
  accelerate_region_id = var.accelerate_region_id
  accelerator_id       = var.accelerator_id
  bandwidth            = var.bandwidth
  ip_version           = var.ip_version

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
  value       = alicloud_ga_ip_set.this.id
}

output "ip_address_list" {
  description = "returns a list of string"
  value       = alicloud_ga_ip_set.this.ip_address_list
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_ip_set.this.status
}

output "this" {
  value = alicloud_ga_ip_set.this
}
```

[top](#index)