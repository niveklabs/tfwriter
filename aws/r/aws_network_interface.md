# aws_network_interface

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_network_interface" {
  source = "./modules/aws/r/aws_network_interface"

  # description - (optional) is a type of string
  description = null
  # ipv6_address_count - (optional) is a type of number
  ipv6_address_count = null
  # ipv6_addresses - (optional) is a type of set of string
  ipv6_addresses = []
  # private_ip - (optional) is a type of string
  private_ip = null
  # private_ips - (optional) is a type of set of string
  private_ips = []
  # private_ips_count - (optional) is a type of number
  private_ips_count = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # source_dest_check - (optional) is a type of bool
  source_dest_check = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  attachment = [{
    attachment_id = null
    device_index  = null
    instance      = null
  }]
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

variable "ipv6_address_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6_addresses" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "private_ips_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "source_dest_check" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "attachment" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      attachment_id = string
      device_index  = number
      instance      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_network_interface" "this" {
  description        = var.description
  ipv6_address_count = var.ipv6_address_count
  ipv6_addresses     = var.ipv6_addresses
  private_ip         = var.private_ip
  private_ips        = var.private_ips
  private_ips_count  = var.private_ips_count
  security_groups    = var.security_groups
  source_dest_check  = var.source_dest_check
  subnet_id          = var.subnet_id
  tags               = var.tags

  dynamic "attachment" {
    for_each = var.attachment
    content {
      device_index = attachment.value["device_index"]
      instance     = attachment.value["instance"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_network_interface.this.id
}

output "ipv6_address_count" {
  description = "returns a number"
  value       = aws_network_interface.this.ipv6_address_count
}

output "ipv6_addresses" {
  description = "returns a set of string"
  value       = aws_network_interface.this.ipv6_addresses
}

output "mac_address" {
  description = "returns a string"
  value       = aws_network_interface.this.mac_address
}

output "outpost_arn" {
  description = "returns a string"
  value       = aws_network_interface.this.outpost_arn
}

output "private_dns_name" {
  description = "returns a string"
  value       = aws_network_interface.this.private_dns_name
}

output "private_ip" {
  description = "returns a string"
  value       = aws_network_interface.this.private_ip
}

output "private_ips" {
  description = "returns a set of string"
  value       = aws_network_interface.this.private_ips
}

output "private_ips_count" {
  description = "returns a number"
  value       = aws_network_interface.this.private_ips_count
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_network_interface.this.security_groups
}

output "this" {
  value = aws_network_interface.this
}
```

[top](#index)