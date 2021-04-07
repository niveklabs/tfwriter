# aws_route53_key_signing_key

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
module "aws_route53_key_signing_key" {
  source = "./modules/aws/r/aws_route53_key_signing_key"

  # hosted_zone_id - (required) is a type of string
  hosted_zone_id = null
  # key_management_service_arn - (required) is a type of string
  key_management_service_arn = null
  # name - (required) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "hosted_zone_id" {
  description = "(required)"
  type        = string
}

variable "key_management_service_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_key_signing_key" "this" {
  # hosted_zone_id - (required) is a type of string
  hosted_zone_id = var.hosted_zone_id
  # key_management_service_arn - (required) is a type of string
  key_management_service_arn = var.key_management_service_arn
  # name - (required) is a type of string
  name = var.name
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "digest_algorithm_mnemonic" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.digest_algorithm_mnemonic
}

output "digest_algorithm_type" {
  description = "returns a number"
  value       = aws_route53_key_signing_key.this.digest_algorithm_type
}

output "digest_value" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.digest_value
}

output "dnskey_record" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.dnskey_record
}

output "ds_record" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.ds_record
}

output "flag" {
  description = "returns a number"
  value       = aws_route53_key_signing_key.this.flag
}

output "id" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.id
}

output "key_tag" {
  description = "returns a number"
  value       = aws_route53_key_signing_key.this.key_tag
}

output "public_key" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.public_key
}

output "signing_algorithm_mnemonic" {
  description = "returns a string"
  value       = aws_route53_key_signing_key.this.signing_algorithm_mnemonic
}

output "signing_algorithm_type" {
  description = "returns a number"
  value       = aws_route53_key_signing_key.this.signing_algorithm_type
}

output "this" {
  value = aws_route53_key_signing_key.this
}
```

[top](#index)