# aws_worklink_website_certificate_authority_association

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
module "aws_worklink_website_certificate_authority_association" {
  source = "./modules/aws/r/aws_worklink_website_certificate_authority_association"

  # certificate - (required) is a type of string
  certificate = null
  # display_name - (optional) is a type of string
  display_name = null
  # fleet_arn - (required) is a type of string
  fleet_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fleet_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_worklink_website_certificate_authority_association" "this" {
  # certificate - (required) is a type of string
  certificate = var.certificate
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # fleet_arn - (required) is a type of string
  fleet_arn = var.fleet_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_worklink_website_certificate_authority_association.this.id
}

output "website_ca_id" {
  description = "returns a string"
  value       = aws_worklink_website_certificate_authority_association.this.website_ca_id
}

output "this" {
  value = aws_worklink_website_certificate_authority_association.this
}
```

[top](#index)