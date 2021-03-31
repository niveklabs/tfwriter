# aws_elastic_beanstalk_application

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elastic_beanstalk_application" {
  source = "./modules/aws/d/aws_elastic_beanstalk_application"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_elastic_beanstalk_application" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "appversion_lifecycle" {
  description = "returns a list of object"
  value       = data.aws_elastic_beanstalk_application.this.appversion_lifecycle
}

output "arn" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_application.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_application.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_elastic_beanstalk_application.this.id
}

output "this" {
  value = aws_elastic_beanstalk_application.this
}
```

[top](#index)