# alicloud_ga_bandwidth_package_attachment

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
module "alicloud_ga_bandwidth_package_attachment" {
  source = "./modules/alicloud/r/alicloud_ga_bandwidth_package_attachment"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # bandwidth_package_id - (required) is a type of string
  bandwidth_package_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "bandwidth_package_id" {
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
resource "alicloud_ga_bandwidth_package_attachment" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # bandwidth_package_id - (required) is a type of string
  bandwidth_package_id = var.bandwidth_package_id

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
output "accelerators" {
  description = "returns a list of string"
  value       = alicloud_ga_bandwidth_package_attachment.this.accelerators
}

output "id" {
  description = "returns a string"
  value       = alicloud_ga_bandwidth_package_attachment.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_ga_bandwidth_package_attachment.this.status
}

output "this" {
  value = alicloud_ga_bandwidth_package_attachment.this
}
```

[top](#index)