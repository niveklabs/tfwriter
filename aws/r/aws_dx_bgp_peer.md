# aws_dx_bgp_peer

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_dx_bgp_peer" {
  source = "./modules/aws/r/aws_dx_bgp_peer"

  # address_family - (required) is a type of string
  address_family = null
  # amazon_address - (optional) is a type of string
  amazon_address = null
  # bgp_asn - (required) is a type of number
  bgp_asn = null
  # bgp_auth_key - (optional) is a type of string
  bgp_auth_key = null
  # customer_address - (optional) is a type of string
  customer_address = null
  # virtual_interface_id - (required) is a type of string
  virtual_interface_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "customer_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_interface_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dx_bgp_peer" "this" {
  address_family       = var.address_family
  amazon_address       = var.amazon_address
  bgp_asn              = var.bgp_asn
  bgp_auth_key         = var.bgp_auth_key
  customer_address     = var.customer_address
  virtual_interface_id = var.virtual_interface_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "amazon_address" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.amazon_address
}

output "aws_device" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.aws_device
}

output "bgp_auth_key" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.bgp_auth_key
}

output "bgp_peer_id" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.bgp_peer_id
}

output "bgp_status" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.bgp_status
}

output "customer_address" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.customer_address
}

output "id" {
  description = "returns a string"
  value       = aws_dx_bgp_peer.this.id
}

output "this" {
  value = aws_dx_bgp_peer.this
}
```

[top](#index)