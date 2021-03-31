# alicloud_cr_ee_namespace

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
module "alicloud_cr_ee_namespace" {
  source = "./modules/alicloud/r/alicloud_cr_ee_namespace"

  # auto_create - (required) is a type of bool
  auto_create = null
  # default_visibility - (required) is a type of string
  default_visibility = null
  # instance_id - (required) is a type of string
  instance_id = null
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

variable "instance_id" {
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
resource "alicloud_cr_ee_namespace" "this" {
  auto_create        = var.auto_create
  default_visibility = var.default_visibility
  instance_id        = var.instance_id
  name               = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cr_ee_namespace.this.id
}

output "this" {
  value = alicloud_cr_ee_namespace.this
}
```

[top](#index)