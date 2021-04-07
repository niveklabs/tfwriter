# aws_rds_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_rds_certificate" {
  source = "./modules/aws/d/aws_rds_certificate"

  # latest_valid_till - (optional) is a type of bool
  latest_valid_till = null
}
```

[top](#index)

### Variables

```terraform
variable "latest_valid_till" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_rds_certificate" "this" {
  # latest_valid_till - (optional) is a type of bool
  latest_valid_till = var.latest_valid_till
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.arn
}

output "certificate_type" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.certificate_type
}

output "customer_override" {
  description = "returns a bool"
  value       = data.aws_rds_certificate.this.customer_override
}

output "customer_override_valid_till" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.customer_override_valid_till
}

output "id" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.id
}

output "thumbprint" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.thumbprint
}

output "valid_from" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.valid_from
}

output "valid_till" {
  description = "returns a string"
  value       = data.aws_rds_certificate.this.valid_till
}

output "this" {
  value = aws_rds_certificate.this
}
```

[top](#index)