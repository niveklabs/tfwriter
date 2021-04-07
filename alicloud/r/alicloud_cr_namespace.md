# alicloud_cr_namespace

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
module "alicloud_cr_namespace" {
  source = "./modules/alicloud/r/alicloud_cr_namespace"

  # auto_create - (required) is a type of bool
  auto_create = null
  # default_visibility - (required) is a type of string
  default_visibility = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_create" {
  description = "(required)"
  type        = bool
}

variable "default_visibility" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cr_namespace" "this" {
  # auto_create - (required) is a type of bool
  auto_create = var.auto_create
  # default_visibility - (required) is a type of string
  default_visibility = var.default_visibility
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cr_namespace.this.id
}

output "this" {
  value = alicloud_cr_namespace.this
}
```

[top](#index)