# alicloud_havip_attachment

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
module "alicloud_havip_attachment" {
  source = "./modules/alicloud/r/alicloud_havip_attachment"

  # havip_id - (required) is a type of string
  havip_id = null
  # instance_id - (required) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "havip_id" {
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
resource "alicloud_havip_attachment" "this" {
  # havip_id - (required) is a type of string
  havip_id = var.havip_id
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_havip_attachment.this.id
}

output "this" {
  value = alicloud_havip_attachment.this
}
```

[top](#index)