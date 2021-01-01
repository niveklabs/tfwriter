# aws_api_gateway_client_certificate

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_api_gateway_client_certificate" {
  source = "./modules/aws/r/aws_api_gateway_client_certificate"

  # description - (optional) is a type of string
  description = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "description" {
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

```hcl
resource "aws_api_gateway_client_certificate" "this" {
  description = var.description
  tags        = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_client_certificate.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_api_gateway_client_certificate.this.created_date
}

output "expiration_date" {
  description = "returns a string"
  value       = aws_api_gateway_client_certificate.this.expiration_date
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_client_certificate.this.id
}

output "pem_encoded_certificate" {
  description = "returns a string"
  value       = aws_api_gateway_client_certificate.this.pem_encoded_certificate
}

output "this" {
  value = aws_api_gateway_client_certificate.this
}
```

[top](#index)