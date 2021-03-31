# alicloud_slb_attachment

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
module "alicloud_slb_attachment" {
  source = "./modules/alicloud/r/alicloud_slb_attachment"

  # backend_servers - (optional) is a type of string
  backend_servers = null
  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # instance_ids - (required) is a type of set of string
  instance_ids = []
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # server_type - (optional) is a type of string
  server_type = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "backend_servers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delete_protection_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_ids" {
  description = "(required)"
  type        = set(string)
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_attachment" "this" {
  backend_servers              = var.backend_servers
  delete_protection_validation = var.delete_protection_validation
  instance_ids                 = var.instance_ids
  load_balancer_id             = var.load_balancer_id
  server_type                  = var.server_type
  weight                       = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "backend_servers" {
  description = "returns a string"
  value       = alicloud_slb_attachment.this.backend_servers
}

output "id" {
  description = "returns a string"
  value       = alicloud_slb_attachment.this.id
}

output "this" {
  value = alicloud_slb_attachment.this
}
```

[top](#index)