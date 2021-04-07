# aws_eip_association

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_eip_association" {
  source = "./modules/aws/r/aws_eip_association"

  # allocation_id - (optional) is a type of string
  allocation_id = null
  # allow_reassociation - (optional) is a type of bool
  allow_reassociation = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # network_interface_id - (optional) is a type of string
  network_interface_id = null
  # private_ip_address - (optional) is a type of string
  private_ip_address = null
  # public_ip - (optional) is a type of string
  public_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "allocation_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_reassociation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_eip_association" "this" {
  # allocation_id - (optional) is a type of string
  allocation_id = var.allocation_id
  # allow_reassociation - (optional) is a type of bool
  allow_reassociation = var.allow_reassociation
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # network_interface_id - (optional) is a type of string
  network_interface_id = var.network_interface_id
  # private_ip_address - (optional) is a type of string
  private_ip_address = var.private_ip_address
  # public_ip - (optional) is a type of string
  public_ip = var.public_ip
}
```

[top](#index)

### Outputs

```terraform
output "allocation_id" {
  description = "returns a string"
  value       = aws_eip_association.this.allocation_id
}

output "id" {
  description = "returns a string"
  value       = aws_eip_association.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = aws_eip_association.this.instance_id
}

output "network_interface_id" {
  description = "returns a string"
  value       = aws_eip_association.this.network_interface_id
}

output "private_ip_address" {
  description = "returns a string"
  value       = aws_eip_association.this.private_ip_address
}

output "public_ip" {
  description = "returns a string"
  value       = aws_eip_association.this.public_ip
}

output "this" {
  value = aws_eip_association.this
}
```

[top](#index)