# aws_acm_certificate_validation

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

```terraform
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
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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

```terraform
resource "aws_acm_certificate_validation" "this" {
  # certificate_arn - (required) is a type of string
  certificate_arn = var.certificate_arn
  # validation_record_fqdns - (optional) is a type of set of string
  validation_record_fqdns = var.validation_record_fqdns

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_acm_certificate_validation.this.id
}

output "this" {
  value = aws_acm_certificate_validation.this
}
```

[top](#index)