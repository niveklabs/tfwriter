# aws_elastic_beanstalk_application
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aws/d/aws_elastic_beanstalk_application"

  # name - (required) is a type of string
  name = null
}
```
[top](#index)
### Variables
```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_elastic_beanstalk_application" "this" {
  name = var.name
}
```
[top](#index)
### Outputs
```hcl
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
