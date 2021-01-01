# aws_imagebuilder_infrastructure_configuration
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
module "aws_imagebuilder_infrastructure_configuration" {
  source = "./modules/aws/d/aws_imagebuilder_infrastructure_configuration"

  # arn - (required) is a type of string
  arn = null
  # resource_tags - (optional) is a type of map of string
  resource_tags = {}
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "arn" {
  description = "(required)"
  type        = string
}

variable "resource_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```
[top](#index)

### Datasource
```hcl
data "aws_imagebuilder_infrastructure_configuration" "this" {
  arn           = var.arn
  resource_tags = var.resource_tags
  tags          = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "date_created" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.date_created
}

output "date_updated" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.date_updated
}

output "description" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.id
}

output "instance_profile_name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.instance_profile_name
}

output "instance_types" {
  description = "returns a set of string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.instance_types
}

output "key_pair" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.key_pair
}

output "logging" {
  description = "returns a list of object"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.logging
}

output "name" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.name
}

output "resource_tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.resource_tags
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.security_group_ids
}

output "sns_topic_arn" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.sns_topic_arn
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.tags
}

output "terminate_instance_on_failure" {
  description = "returns a bool"
  value       = data.aws_imagebuilder_infrastructure_configuration.this.terminate_instance_on_failure
}

output "this" {
  value = aws_imagebuilder_infrastructure_configuration.this
}
```
[top](#index)
