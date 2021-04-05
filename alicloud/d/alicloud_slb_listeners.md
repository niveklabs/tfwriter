# alicloud_slb_listeners

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_slb_listeners" {
  source = "./modules/alicloud/d/alicloud_slb_listeners"

  # description_regex - (optional) is a type of string
  description_regex = null
  # frontend_port - (optional) is a type of number
  frontend_port = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # protocol - (optional) is a type of string
  protocol = null
}
```

[top](#index)

### Variables

```terraform
variable "description_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frontend_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_slb_listeners" "this" {
  description_regex = var.description_regex
  frontend_port     = var.frontend_port
  load_balancer_id  = var.load_balancer_id
  output_file       = var.output_file
  protocol          = var.protocol
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_slb_listeners.this.id
}

output "slb_listeners" {
  description = "returns a list of object"
  value       = data.alicloud_slb_listeners.this.slb_listeners
}

output "this" {
  value = alicloud_slb_listeners.this
}
```

[top](#index)