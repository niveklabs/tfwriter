# aws_iot_certificate

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
module "aws_iot_certificate" {
  source = "./modules/aws/r/aws_iot_certificate"

  # active - (required) is a type of bool
  active = null
  # csr - (optional) is a type of string
  csr = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(required)"
  type        = bool
}

variable "csr" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_certificate" "this" {
  # active - (required) is a type of bool
  active = var.active
  # csr - (optional) is a type of string
  csr = var.csr
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iot_certificate.this.arn
}

output "certificate_pem" {
  description = "returns a string"
  value       = aws_iot_certificate.this.certificate_pem
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = aws_iot_certificate.this.id
}

output "private_key" {
  description = "returns a string"
  value       = aws_iot_certificate.this.private_key
  sensitive   = true
}

output "public_key" {
  description = "returns a string"
  value       = aws_iot_certificate.this.public_key
  sensitive   = true
}

output "this" {
  value = aws_iot_certificate.this
}
```

[top](#index)