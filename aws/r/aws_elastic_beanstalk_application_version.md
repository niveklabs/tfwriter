# aws_elastic_beanstalk_application_version

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

```hcl
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

```hcl
resource "aws_elastic_beanstalk_application_version" "this" {
  application  = var.application
  bucket       = var.bucket
  description  = var.description
  force_delete = var.force_delete
  key          = var.key
  name         = var.name
  tags         = var.tags
}
```

[top](#index)

### Outputs

```hcl
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