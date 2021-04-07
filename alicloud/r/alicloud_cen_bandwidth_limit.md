# alicloud_cen_bandwidth_limit

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
module "alicloud_cen_bandwidth_limit" {
  source = "./modules/alicloud/r/alicloud_cen_bandwidth_limit"

  # bandwidth_limit - (required) is a type of number
  bandwidth_limit = null
  # instance_id - (required) is a type of string
  instance_id = null
  # region_ids - (required) is a type of set of string
  region_ids = []

  timeouts = [{
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_limit" {
  description = "(required)"
  type        = number
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "region_ids" {
  description = "(required)"
  type        = set(string)
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
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
resource "alicloud_cen_bandwidth_limit" "this" {
  # bandwidth_limit - (required) is a type of number
  bandwidth_limit = var.bandwidth_limit
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # region_ids - (required) is a type of set of string
  region_ids = var.region_ids

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = alicloud_cen_bandwidth_limit.this.id
}

output "this" {
  value = alicloud_cen_bandwidth_limit.this
}
```

[top](#index)