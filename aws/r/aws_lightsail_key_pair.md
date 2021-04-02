# aws_lightsail_key_pair

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
module "aws_lightsail_key_pair" {
  source = "./modules/aws/r/aws_lightsail_key_pair"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # pgp_key - (optional) is a type of string
  pgp_key = null
  # public_key - (optional) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_lightsail_key_pair" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  pgp_key     = var.pgp_key
  public_key  = var.public_key
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.arn
}

output "encrypted_fingerprint" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.encrypted_fingerprint
}

output "encrypted_private_key" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.encrypted_private_key
}

output "fingerprint" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.name
}

output "private_key" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.private_key
}

output "public_key" {
  description = "returns a string"
  value       = aws_lightsail_key_pair.this.public_key
}

output "this" {
  value = aws_lightsail_key_pair.this
}
```

[top](#index)