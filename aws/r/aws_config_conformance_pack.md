# aws_config_conformance_pack

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
module "aws_config_conformance_pack" {
  source = "./modules/aws/r/aws_config_conformance_pack"

  # delivery_s3_bucket - (optional) is a type of string
  delivery_s3_bucket = null
  # delivery_s3_key_prefix - (optional) is a type of string
  delivery_s3_key_prefix = null
  # name - (required) is a type of string
  name = null
  # template_body - (optional) is a type of string
  template_body = null
  # template_s3_uri - (optional) is a type of string
  template_s3_uri = null

  input_parameter = [{
    parameter_name  = null
    parameter_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delivery_s3_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delivery_s3_key_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_s3_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_parameter" {
  description = "nested block: NestingSet, min items: 0, max items: 60"
  type = set(object(
    {
      parameter_name  = string
      parameter_value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_conformance_pack" "this" {
  # delivery_s3_bucket - (optional) is a type of string
  delivery_s3_bucket = var.delivery_s3_bucket
  # delivery_s3_key_prefix - (optional) is a type of string
  delivery_s3_key_prefix = var.delivery_s3_key_prefix
  # name - (required) is a type of string
  name = var.name
  # template_body - (optional) is a type of string
  template_body = var.template_body
  # template_s3_uri - (optional) is a type of string
  template_s3_uri = var.template_s3_uri

  dynamic "input_parameter" {
    for_each = var.input_parameter
    content {
      # parameter_name - (required) is a type of string
      parameter_name = input_parameter.value["parameter_name"]
      # parameter_value - (required) is a type of string
      parameter_value = input_parameter.value["parameter_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_config_conformance_pack.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_conformance_pack.this.id
}

output "this" {
  value = aws_config_conformance_pack.this
}
```

[top](#index)