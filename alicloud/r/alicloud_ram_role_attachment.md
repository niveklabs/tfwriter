# alicloud_ram_role_attachment

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
module "alicloud_ram_role_attachment" {
  source = "./modules/alicloud/r/alicloud_ram_role_attachment"

  # instance_ids - (required) is a type of set of string
  instance_ids = []
  # role_name - (required) is a type of string
  role_name = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_ids" {
  description = "(required)"
  type        = set(string)
}

variable "role_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_role_attachment" "this" {
  instance_ids = var.instance_ids
  role_name    = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_role_attachment.this.id
}

output "this" {
  value = alicloud_ram_role_attachment.this
}
```

[top](#index)