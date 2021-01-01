# aws_dms_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_dms_certificate" {
  source = "./modules/aws/r/aws_dms_certificate"

  # certificate_id - (required) is a type of string
  certificate_id = null
  # certificate_pem - (optional) is a type of string
  certificate_pem = null
  # certificate_wallet - (optional) is a type of string
  certificate_wallet = null
}
```

[top](#index)

### Variables

```hcl
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
```

[top](#index)

### Resource

```hcl
resource "aws_dms_certificate" "this" {
  certificate_id     = var.certificate_id
  certificate_pem    = var.certificate_pem
  certificate_wallet = var.certificate_wallet
}
```

[top](#index)

### Outputs

```hcl
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