# aws_ecs_container_definition
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
module "aws_ecs_container_definition" {
  source = "./modules/aws/d/aws_ecs_container_definition"

  # container_name - (required) is a type of string
  container_name = null
  # task_definition - (required) is a type of string
  task_definition = null
}
```
[top](#index)
### Variables
```hcl
variable "container_name" {
  description = "(required)"
  type        = string
}

variable "task_definition" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Datasource
```hcl
data "aws_ecs_container_definition" "this" {
  container_name  = var.container_name
  task_definition = var.task_definition
}
```
[top](#index)
### Outputs
```hcl
output "cpu" {
  description = "returns a number"
  value       = data.aws_ecs_container_definition.this.cpu
}

output "disable_networking" {
  description = "returns a bool"
  value       = data.aws_ecs_container_definition.this.disable_networking
}

output "docker_labels" {
  description = "returns a map of string"
  value       = data.aws_ecs_container_definition.this.docker_labels
}

output "environment" {
  description = "returns a map of string"
  value       = data.aws_ecs_container_definition.this.environment
}

output "id" {
  description = "returns a string"
  value       = data.aws_ecs_container_definition.this.id
}

output "image" {
  description = "returns a string"
  value       = data.aws_ecs_container_definition.this.image
}

output "image_digest" {
  description = "returns a string"
  value       = data.aws_ecs_container_definition.this.image_digest
}

output "memory" {
  description = "returns a number"
  value       = data.aws_ecs_container_definition.this.memory
}

output "memory_reservation" {
  description = "returns a number"
  value       = data.aws_ecs_container_definition.this.memory_reservation
}

output "this" {
  value = aws_ecs_container_definition.this
}
```
[top](#index)
