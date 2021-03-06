# aws_elastic_beanstalk_application_version

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
module "aws_elastic_beanstalk_application_version" {
  source = "./modules/aws/r/aws_elastic_beanstalk_application_version"

  # application - (required) is a type of string
  application = null
  # bucket - (required) is a type of string
  bucket = null
  # description - (optional) is a type of string
  description = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "application" {
  description = "(required)"
  type        = string
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "aws_elastic_beanstalk_application_version" "this" {
  # application - (required) is a type of string
  application = var.application
  # bucket - (required) is a type of string
  bucket = var.bucket
  # description - (optional) is a type of string
  description = var.description
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # key - (required) is a type of string
  key = var.key
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_application_version.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_application_version.this.id
}

output "this" {
  value = aws_elastic_beanstalk_application_version.this
}
```

[top](#index)