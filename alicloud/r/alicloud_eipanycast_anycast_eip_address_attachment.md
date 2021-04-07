# alicloud_eipanycast_anycast_eip_address_attachment

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
module "alicloud_eipanycast_anycast_eip_address_attachment" {
  source = "./modules/alicloud/r/alicloud_eipanycast_anycast_eip_address_attachment"

  # anycast_id - (required) is a type of string
  anycast_id = null
  # bind_instance_id - (required) is a type of string
  bind_instance_id = null
  # bind_instance_region_id - (required) is a type of string
  bind_instance_region_id = null
  # bind_instance_type - (required) is a type of string
  bind_instance_type = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "anycast_id" {
  description = "(required)"
  type        = string
}

variable "bind_instance_id" {
  description = "(required)"
  type        = string
}

variable "bind_instance_region_id" {
  description = "(required)"
  type        = string
}

variable "bind_instance_type" {
  description = "(required)"
  type        = string
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
resource "alicloud_eipanycast_anycast_eip_address_attachment" "this" {
  # anycast_id - (required) is a type of string
  anycast_id = var.anycast_id
  # bind_instance_id - (required) is a type of string
  bind_instance_id = var.bind_instance_id
  # bind_instance_region_id - (required) is a type of string
  bind_instance_region_id = var.bind_instance_region_id
  # bind_instance_type - (required) is a type of string
  bind_instance_type = var.bind_instance_type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bind_time" {
  description = "returns a string"
  value       = alicloud_eipanycast_anycast_eip_address_attachment.this.bind_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_eipanycast_anycast_eip_address_attachment.this.id
}

output "this" {
  value = alicloud_eipanycast_anycast_eip_address_attachment.this
}
```

[top](#index)