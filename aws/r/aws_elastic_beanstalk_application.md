# aws_elastic_beanstalk_application

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
module "aws_elastic_beanstalk_application" {
  source = "./modules/aws/r/aws_elastic_beanstalk_application"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  appversion_lifecycle = [{
    delete_source_from_s3 = null
    max_age_in_days       = null
    max_count             = null
    service_role          = null
  }]
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "appversion_lifecycle" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_source_from_s3 = bool
      max_age_in_days       = number
      max_count             = number
      service_role          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_elastic_beanstalk_application" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "appversion_lifecycle" {
    for_each = var.appversion_lifecycle
    content {
      delete_source_from_s3 = appversion_lifecycle.value["delete_source_from_s3"]
      max_age_in_days       = appversion_lifecycle.value["max_age_in_days"]
      max_count             = appversion_lifecycle.value["max_count"]
      service_role          = appversion_lifecycle.value["service_role"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_application.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_application.this.id
}

output "this" {
  value = aws_elastic_beanstalk_application.this
}
```

[top](#index)