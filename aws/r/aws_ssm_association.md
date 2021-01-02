# aws_ssm_association

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ssm_association" {
  source = "./modules/aws/r/aws_ssm_association"

  # association_name - (optional) is a type of string
  association_name = null
  # automation_target_parameter_name - (optional) is a type of string
  automation_target_parameter_name = null
  # compliance_severity - (optional) is a type of string
  compliance_severity = null
  # document_version - (optional) is a type of string
  document_version = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # max_concurrency - (optional) is a type of string
  max_concurrency = null
  # max_errors - (optional) is a type of string
  max_errors = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # schedule_expression - (optional) is a type of string
  schedule_expression = null

  output_location = [{
    s3_bucket_name = null
    s3_key_prefix  = null
  }]

  targets = [{
    key    = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "association_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "automation_target_parameter_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compliance_severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "document_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_concurrency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_errors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "schedule_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_location" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      s3_bucket_name = string
      s3_key_prefix  = string
    }
  ))
  default = []
}

variable "targets" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      key    = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_association" "this" {
  association_name                 = var.association_name
  automation_target_parameter_name = var.automation_target_parameter_name
  compliance_severity              = var.compliance_severity
  document_version                 = var.document_version
  instance_id                      = var.instance_id
  max_concurrency                  = var.max_concurrency
  max_errors                       = var.max_errors
  name                             = var.name
  parameters                       = var.parameters
  schedule_expression              = var.schedule_expression

  dynamic "output_location" {
    for_each = var.output_location
    content {
      s3_bucket_name = output_location.value["s3_bucket_name"]
      s3_key_prefix  = output_location.value["s3_key_prefix"]
    }
  }

  dynamic "targets" {
    for_each = var.targets
    content {
      key    = targets.value["key"]
      values = targets.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "association_id" {
  description = "returns a string"
  value       = aws_ssm_association.this.association_id
}

output "document_version" {
  description = "returns a string"
  value       = aws_ssm_association.this.document_version
}

output "id" {
  description = "returns a string"
  value       = aws_ssm_association.this.id
}

output "parameters" {
  description = "returns a map of string"
  value       = aws_ssm_association.this.parameters
}

output "this" {
  value = aws_ssm_association.this
}
```

[top](#index)