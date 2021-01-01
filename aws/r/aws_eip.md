# aws_eip
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
module "aws_eip" {
  source = "./modules/aws/r/aws_eip"

  # associate_with_private_ip - (optional) is a type of string
  associate_with_private_ip = null
  # customer_owned_ipv4_pool - (optional) is a type of string
  customer_owned_ipv4_pool = null
  # instance - (optional) is a type of string
  instance = null
  # network_border_group - (optional) is a type of string
  network_border_group = null
  # network_interface - (optional) is a type of string
  network_interface = null
  # public_ipv4_pool - (optional) is a type of string
  public_ipv4_pool = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc - (optional) is a type of bool
  vpc = null

  timeouts = [{
    delete = null
    read   = null
    update = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "associate_with_private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customer_owned_ipv4_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_border_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ipv4_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_eip" "this" {
  associate_with_private_ip = var.associate_with_private_ip
  customer_owned_ipv4_pool  = var.customer_owned_ipv4_pool
  instance                  = var.instance
  network_border_group      = var.network_border_group
  network_interface         = var.network_interface
  public_ipv4_pool          = var.public_ipv4_pool
  tags                      = var.tags
  vpc                       = var.vpc

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "allocation_id" {
  description = "returns a string"
  value       = aws_eip.this.allocation_id
}

output "association_id" {
  description = "returns a string"
  value       = aws_eip.this.association_id
}

output "carrier_ip" {
  description = "returns a string"
  value       = aws_eip.this.carrier_ip
}

output "customer_owned_ip" {
  description = "returns a string"
  value       = aws_eip.this.customer_owned_ip
}

output "domain" {
  description = "returns a string"
  value       = aws_eip.this.domain
}

output "id" {
  description = "returns a string"
  value       = aws_eip.this.id
}

output "instance" {
  description = "returns a string"
  value       = aws_eip.this.instance
}

output "network_border_group" {
  description = "returns a string"
  value       = aws_eip.this.network_border_group
}

output "network_interface" {
  description = "returns a string"
  value       = aws_eip.this.network_interface
}

output "private_dns" {
  description = "returns a string"
  value       = aws_eip.this.private_dns
}

output "private_ip" {
  description = "returns a string"
  value       = aws_eip.this.private_ip
}

output "public_dns" {
  description = "returns a string"
  value       = aws_eip.this.public_dns
}

output "public_ip" {
  description = "returns a string"
  value       = aws_eip.this.public_ip
}

output "public_ipv4_pool" {
  description = "returns a string"
  value       = aws_eip.this.public_ipv4_pool
}

output "vpc" {
  description = "returns a bool"
  value       = aws_eip.this.vpc
}

output "this" {
  value = aws_eip.this
}
```
[top](#index)
