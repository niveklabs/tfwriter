# aws_acm_certificate_validation
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
module "aws_acm_certificate_validation" {
  source = "./modules/aws/r/aws_acm_certificate_validation"

  # certificate_arn - (required) is a type of string
  certificate_arn = null
  # validation_record_fqdns - (optional) is a type of set of string
  validation_record_fqdns = []

  timeouts = [{
    create = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "certificate_arn" {
  description = "(required)"
  type        = string
}

variable "validation_record_fqdns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_acm_certificate_validation" "this" {
  certificate_arn         = var.certificate_arn
  validation_record_fqdns = var.validation_record_fqdns

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_acm_certificate_validation.this.id
}

output "this" {
  value = aws_acm_certificate_validation.this
}
```
[top](#index)
