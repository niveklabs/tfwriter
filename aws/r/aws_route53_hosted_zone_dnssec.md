# aws_route53_hosted_zone_dnssec

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
module "aws_route53_hosted_zone_dnssec" {
  source = "./modules/aws/r/aws_route53_hosted_zone_dnssec"

  # hosted_zone_id - (required) is a type of string
  hosted_zone_id = null
  # signing_status - (optional) is a type of string
  signing_status = null
}
```

[top](#index)

### Variables

```terraform
variable "hosted_zone_id" {
  description = "(required)"
  type        = string
}

variable "signing_status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_hosted_zone_dnssec" "this" {
  # hosted_zone_id - (required) is a type of string
  hosted_zone_id = var.hosted_zone_id
  # signing_status - (optional) is a type of string
  signing_status = var.signing_status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_route53_hosted_zone_dnssec.this.id
}

output "this" {
  value = aws_route53_hosted_zone_dnssec.this
}
```

[top](#index)