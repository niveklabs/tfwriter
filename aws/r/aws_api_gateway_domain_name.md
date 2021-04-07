# aws_api_gateway_domain_name

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
module "aws_api_gateway_domain_name" {
  source = "./modules/aws/r/aws_api_gateway_domain_name"

  # certificate_arn - (optional) is a type of string
  certificate_arn = null
  # certificate_body - (optional) is a type of string
  certificate_body = null
  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # certificate_name - (optional) is a type of string
  certificate_name = null
  # certificate_private_key - (optional) is a type of string
  certificate_private_key = null
  # domain_name - (required) is a type of string
  domain_name = null
  # regional_certificate_arn - (optional) is a type of string
  regional_certificate_arn = null
  # regional_certificate_name - (optional) is a type of string
  regional_certificate_name = null
  # security_policy - (optional) is a type of string
  security_policy = null
  # tags - (optional) is a type of map of string
  tags = {}

  endpoint_configuration = [{
    types = []
  }]

  mutual_tls_authentication = [{
    truststore_uri     = null
    truststore_version = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "regional_certificate_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "regional_certificate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "endpoint_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      types = list(string)
    }
  ))
  default = []
}

variable "mutual_tls_authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      truststore_uri     = string
      truststore_version = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_domain_name" "this" {
  # certificate_arn - (optional) is a type of string
  certificate_arn = var.certificate_arn
  # certificate_body - (optional) is a type of string
  certificate_body = var.certificate_body
  # certificate_chain - (optional) is a type of string
  certificate_chain = var.certificate_chain
  # certificate_name - (optional) is a type of string
  certificate_name = var.certificate_name
  # certificate_private_key - (optional) is a type of string
  certificate_private_key = var.certificate_private_key
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # regional_certificate_arn - (optional) is a type of string
  regional_certificate_arn = var.regional_certificate_arn
  # regional_certificate_name - (optional) is a type of string
  regional_certificate_name = var.regional_certificate_name
  # security_policy - (optional) is a type of string
  security_policy = var.security_policy
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "endpoint_configuration" {
    for_each = var.endpoint_configuration
    content {
      # types - (required) is a type of list of string
      types = endpoint_configuration.value["types"]
    }
  }

  dynamic "mutual_tls_authentication" {
    for_each = var.mutual_tls_authentication
    content {
      # truststore_uri - (required) is a type of string
      truststore_uri = mutual_tls_authentication.value["truststore_uri"]
      # truststore_version - (optional) is a type of string
      truststore_version = mutual_tls_authentication.value["truststore_version"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.arn
}

output "certificate_upload_date" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.certificate_upload_date
}

output "cloudfront_domain_name" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.cloudfront_domain_name
}

output "cloudfront_zone_id" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.cloudfront_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.id
}

output "regional_domain_name" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.regional_domain_name
}

output "regional_zone_id" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.regional_zone_id
}

output "security_policy" {
  description = "returns a string"
  value       = aws_api_gateway_domain_name.this.security_policy
}

output "this" {
  value = aws_api_gateway_domain_name.this
}
```

[top](#index)