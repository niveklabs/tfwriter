# tencentcloud_placement_group

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_placement_group" {
  source = "./modules/tencentcloud/r/tencentcloud_placement_group"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the placement group, 1-60 characters in length."
  type        = string
}

variable "type" {
  description = "(required) - Type of the placement group. Valid values: `HOST`, `SW` and `RACK`."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_placement_group" "this" {
  name = var.name
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_placement_group.this.create_time
}

output "current_num" {
  description = "returns a number"
  value       = tencentcloud_placement_group.this.current_num
}

output "cvm_quota_total" {
  description = "returns a number"
  value       = tencentcloud_placement_group.this.cvm_quota_total
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_placement_group.this.id
}

output "this" {
  value = tencentcloud_placement_group.this
}
```

[top](#index)