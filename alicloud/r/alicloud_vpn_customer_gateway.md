# alicloud_vpn_customer_gateway

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
module "alicloud_vpn_customer_gateway" {
  source = "./modules/alicloud/r/alicloud_vpn_customer_gateway"

  # description - (optional) is a type of string
  description = null
  # ip_address - (required) is a type of string
  ip_address = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_vpn_customer_gateway" "this" {
  description = var.description
  ip_address  = var.ip_address
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_vpn_customer_gateway.this.id
}

output "this" {
  value = alicloud_vpn_customer_gateway.this
}
```

[top](#index)