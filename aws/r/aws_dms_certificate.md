# aws_dms_certificate

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
module "aws_dms_certificate" {
  source = "./modules/aws/r/aws_dms_certificate"

  # certificate_id - (required) is a type of string
  certificate_id = null
  # certificate_pem - (optional) is a type of string
  certificate_pem = null
  # certificate_wallet - (optional) is a type of string
  certificate_wallet = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(required)"
  type        = string
}

variable "certificate_pem" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_wallet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_certificate" "this" {
  certificate_id     = var.certificate_id
  certificate_pem    = var.certificate_pem
  certificate_wallet = var.certificate_wallet
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "certificate_arn" {
  description = "returns a string"
  value       = aws_dms_certificate.this.certificate_arn
}

output "id" {
  description = "returns a string"
  value       = aws_dms_certificate.this.id
}

output "this" {
  value = aws_dms_certificate.this
}
```

[top](#index)