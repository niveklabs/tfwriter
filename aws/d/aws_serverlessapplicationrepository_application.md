# aws_serverlessapplicationrepository_application

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_serverlessapplicationrepository_application" {
  source = "./modules/aws/d/aws_serverlessapplicationrepository_application"

  # application_id - (required) is a type of string
  application_id = null
  # semantic_version - (optional) is a type of string
  semantic_version = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "semantic_version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_serverlessapplicationrepository_application" "this" {
  # application_id - (required) is a type of string
  application_id = var.application_id
  # semantic_version - (optional) is a type of string
  semantic_version = var.semantic_version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_serverlessapplicationrepository_application.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_serverlessapplicationrepository_application.this.name
}

output "required_capabilities" {
  description = "returns a set of string"
  value       = data.aws_serverlessapplicationrepository_application.this.required_capabilities
}

output "semantic_version" {
  description = "returns a string"
  value       = data.aws_serverlessapplicationrepository_application.this.semantic_version
}

output "source_code_url" {
  description = "returns a string"
  value       = data.aws_serverlessapplicationrepository_application.this.source_code_url
}

output "template_url" {
  description = "returns a string"
  value       = data.aws_serverlessapplicationrepository_application.this.template_url
}

output "this" {
  value = aws_serverlessapplicationrepository_application.this
}
```

[top](#index)