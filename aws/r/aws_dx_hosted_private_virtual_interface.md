# aws_dx_hosted_private_virtual_interface

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_dx_hosted_private_virtual_interface" {
  source = "./modules/aws/r/aws_dx_hosted_private_virtual_interface"

  # address_family - (required) is a type of string
  address_family = null
  # amazon_address - (optional) is a type of string
  amazon_address = null
  # bgp_asn - (required) is a type of number
  bgp_asn = null
  # bgp_auth_key - (optional) is a type of string
  bgp_auth_key = null
  # connection_id - (required) is a type of string
  connection_id = null
  # customer_address - (optional) is a type of string
  customer_address = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # owner_account_id - (required) is a type of string
  owner_account_id = null
  # vlan - (required) is a type of number
  vlan = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "address_family" {
  description = "(required)"
  type        = string
}

variable "amazon_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_asn" {
  description = "(required)"
  type        = number
}

variable "bgp_auth_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_id" {
  description = "(required)"
  type        = string
}

variable "customer_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_account_id" {
  description = "(required)"
  type        = string
}

variable "vlan" {
  description = "(required)"
  type        = number
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_dx_hosted_private_virtual_interface" "this" {
  address_family   = var.address_family
  amazon_address   = var.amazon_address
  bgp_asn          = var.bgp_asn
  bgp_auth_key     = var.bgp_auth_key
  connection_id    = var.connection_id
  customer_address = var.customer_address
  mtu              = var.mtu
  name             = var.name
  owner_account_id = var.owner_account_id
  vlan             = var.vlan

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "amazon_address" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.amazon_address
}

output "amazon_side_asn" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.amazon_side_asn
}

output "arn" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.arn
}

output "aws_device" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.aws_device
}

output "bgp_auth_key" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.bgp_auth_key
}

output "customer_address" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.customer_address
}

output "id" {
  description = "returns a string"
  value       = aws_dx_hosted_private_virtual_interface.this.id
}

output "jumbo_frame_capable" {
  description = "returns a bool"
  value       = aws_dx_hosted_private_virtual_interface.this.jumbo_frame_capable
}

output "this" {
  value = aws_dx_hosted_private_virtual_interface.this
}
```

[top](#index)