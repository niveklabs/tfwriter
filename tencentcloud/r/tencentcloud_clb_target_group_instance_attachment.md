# tencentcloud_clb_target_group_instance_attachment

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
module "tencentcloud_clb_target_group_instance_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_target_group_instance_attachment"

  # bind_ip - (required) is a type of string
  bind_ip = null
  # port - (required) is a type of number
  port = null
  # target_group_id - (required) is a type of string
  target_group_id = null
  # weight - (required) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "bind_ip" {
  description = "(required) - The Intranet IP of the target group instance."
  type        = string
}

variable "port" {
  description = "(required) - Port of the target group instance."
  type        = number
}

variable "target_group_id" {
  description = "(required) - Target group ID."
  type        = string
}

variable "weight" {
  description = "(required) - The weight of the target group instance."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_target_group_instance_attachment" "this" {
  # bind_ip - (required) is a type of string
  bind_ip = var.bind_ip
  # port - (required) is a type of number
  port = var.port
  # target_group_id - (required) is a type of string
  target_group_id = var.target_group_id
  # weight - (required) is a type of number
  weight = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_target_group_instance_attachment.this.id
}

output "this" {
  value = tencentcloud_clb_target_group_instance_attachment.this
}
```

[top](#index)