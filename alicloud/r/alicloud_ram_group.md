# alicloud_ram_group

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_group" {
  source = "./modules/alicloud/r/alicloud_ram_group"

  # comments - (optional) is a type of string
  comments = null
  # force - (optional) is a type of bool
  force = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_group" "this" {
  comments = var.comments
  force    = var.force
  name     = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_group.this.id
}

output "this" {
  value = alicloud_ram_group.this
}
```

[top](#index)