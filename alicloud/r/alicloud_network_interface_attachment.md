# alicloud_network_interface_attachment

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
module "alicloud_network_interface_attachment" {
  source = "./modules/alicloud/r/alicloud_network_interface_attachment"

  # instance_id - (required) is a type of string
  instance_id = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "network_interface_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_network_interface_attachment" "this" {
  instance_id          = var.instance_id
  network_interface_id = var.network_interface_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_network_interface_attachment.this.id
}

output "this" {
  value = alicloud_network_interface_attachment.this
}
```

[top](#index)