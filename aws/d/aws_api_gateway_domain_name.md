# aws_api_gateway_domain_name

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
module "aws_api_gateway_domain_name" {
  source = "./modules/aws/d/aws_api_gateway_domain_name"

  # domain_name - (required) is a type of string
  domain_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_api_gateway_domain_name" "this" {
  domain_name = var.domain_name
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.arn
}

output "certificate_arn" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.certificate_arn
}

output "certificate_name" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.certificate_name
}

output "certificate_upload_date" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.certificate_upload_date
}

output "cloudfront_domain_name" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.cloudfront_domain_name
}

output "cloudfront_zone_id" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.cloudfront_zone_id
}

output "endpoint_configuration" {
  description = "returns a list of object"
  value       = data.aws_api_gateway_domain_name.this.endpoint_configuration
}

output "id" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.id
}

output "regional_certificate_arn" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.regional_certificate_arn
}

output "regional_certificate_name" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.regional_certificate_name
}

output "regional_domain_name" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.regional_domain_name
}

output "regional_zone_id" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.regional_zone_id
}

output "security_policy" {
  description = "returns a string"
  value       = data.aws_api_gateway_domain_name.this.security_policy
}

output "this" {
  value = aws_api_gateway_domain_name.this
}
```

[top](#index)