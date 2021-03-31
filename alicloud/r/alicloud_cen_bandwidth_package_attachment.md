# alicloud_cen_bandwidth_package_attachment

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
module "alicloud_cen_bandwidth_package_attachment" {
  source = "./modules/alicloud/r/alicloud_cen_bandwidth_package_attachment"

  # bandwidth_package_id - (required) is a type of string
  bandwidth_package_id = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth_package_id" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_bandwidth_package_attachment" "this" {
  bandwidth_package_id = var.bandwidth_package_id
  instance_id          = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_bandwidth_package_attachment.this.id
}

output "this" {
  value = alicloud_cen_bandwidth_package_attachment.this
}
```

[top](#index)