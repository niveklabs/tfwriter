# alicloud_cen_instance_grant

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
module "alicloud_cen_instance_grant" {
  source = "./modules/alicloud/r/alicloud_cen_instance_grant"

  # cen_id - (required) is a type of string
  cen_id = null
  # cen_owner_id - (required) is a type of string
  cen_owner_id = null
  # child_instance_id - (required) is a type of string
  child_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "cen_owner_id" {
  description = "(required)"
  type        = string
}

variable "child_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_instance_grant" "this" {
  cen_id            = var.cen_id
  cen_owner_id      = var.cen_owner_id
  child_instance_id = var.child_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_instance_grant.this.id
}

output "this" {
  value = alicloud_cen_instance_grant.this
}
```

[top](#index)