# alicloud_ess_attachment

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
module "alicloud_ess_attachment" {
  source = "./modules/alicloud/r/alicloud_ess_attachment"

  # force - (optional) is a type of bool
  force = null
  # instance_ids - (required) is a type of set of string
  instance_ids = []
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_ids" {
  description = "(required)"
  type        = set(string)
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_attachment" "this" {
  force            = var.force
  instance_ids     = var.instance_ids
  scaling_group_id = var.scaling_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ess_attachment.this.id
}

output "this" {
  value = alicloud_ess_attachment.this
}
```

[top](#index)