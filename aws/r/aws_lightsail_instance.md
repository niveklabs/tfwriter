# aws_lightsail_instance

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
module "aws_lightsail_instance" {
  source = "./modules/aws/r/aws_lightsail_instance"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # blueprint_id - (required) is a type of string
  blueprint_id = null
  # bundle_id - (required) is a type of string
  bundle_id = null
  # key_pair_name - (optional) is a type of string
  key_pair_name = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_data - (optional) is a type of string
  user_data = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
}

variable "blueprint_id" {
  description = "(required)"
  type        = string
}

variable "bundle_id" {
  description = "(required)"
  type        = string
}

variable "key_pair_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_lightsail_instance" "this" {
  availability_zone = var.availability_zone
  blueprint_id      = var.blueprint_id
  bundle_id         = var.bundle_id
  key_pair_name     = var.key_pair_name
  name              = var.name
  tags              = var.tags
  user_data         = var.user_data
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.arn
}

output "cpu_count" {
  description = "returns a number"
  value       = aws_lightsail_instance.this.cpu_count
}

output "created_at" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.created_at
}

output "id" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.id
}

output "ipv6_address" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.ipv6_address
}

output "ipv6_addresses" {
  description = "returns a list of string"
  value       = aws_lightsail_instance.this.ipv6_addresses
}

output "is_static_ip" {
  description = "returns a bool"
  value       = aws_lightsail_instance.this.is_static_ip
}

output "private_ip_address" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.private_ip_address
}

output "public_ip_address" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.public_ip_address
}

output "ram_size" {
  description = "returns a number"
  value       = aws_lightsail_instance.this.ram_size
}

output "username" {
  description = "returns a string"
  value       = aws_lightsail_instance.this.username
}

output "this" {
  value = aws_lightsail_instance.this
}
```

[top](#index)