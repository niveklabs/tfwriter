# alicloud_slb_domain_extension

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
module "alicloud_slb_domain_extension" {
  source = "./modules/alicloud/r/alicloud_slb_domain_extension"

  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # domain - (required) is a type of string
  domain = null
  # frontend_port - (required) is a type of number
  frontend_port = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # server_certificate_id - (required) is a type of string
  server_certificate_id = null
}
```

[top](#index)

### Variables

```terraform
variable "delete_protection_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "frontend_port" {
  description = "(required)"
  type        = number
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "server_certificate_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_domain_extension" "this" {
  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = var.delete_protection_validation
  # domain - (required) is a type of string
  domain = var.domain
  # frontend_port - (required) is a type of number
  frontend_port = var.frontend_port
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id
  # server_certificate_id - (required) is a type of string
  server_certificate_id = var.server_certificate_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_domain_extension.this.id
}

output "this" {
  value = alicloud_slb_domain_extension.this
}
```

[top](#index)