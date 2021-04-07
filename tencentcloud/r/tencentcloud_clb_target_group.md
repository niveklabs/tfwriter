# tencentcloud_clb_target_group

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
module "tencentcloud_clb_target_group" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_target_group"

  # target_group_name - (optional) is a type of string
  target_group_name = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "target_group_name" {
  description = "(optional) - Target group name."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - VPC ID, default is based on the network."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_target_group" "this" {
  target_group_name = var.target_group_name
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_target_group.this.id
}

output "this" {
  value = tencentcloud_clb_target_group.this
}
```

[top](#index)