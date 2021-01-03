# alicloud_slb_domain_extensions

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_domain_extensions" {
  source = "./modules/alicloud/d/alicloud_slb_domain_extensions"

  # frontend_port - (required) is a type of number
  frontend_port = null
  # ids - (optional) is a type of list of string
  ids = []
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "frontend_port" {
  description = "(required)"
  type        = number
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_slb_domain_extensions" "this" {
  frontend_port    = var.frontend_port
  ids              = var.ids
  load_balancer_id = var.load_balancer_id
  output_file      = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "extensions" {
  description = "returns a list of object"
  value       = data.alicloud_slb_domain_extensions.this.extensions
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_slb_domain_extensions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_slb_domain_extensions.this.ids
}

output "this" {
  value = alicloud_slb_domain_extensions.this
}
```

[top](#index)