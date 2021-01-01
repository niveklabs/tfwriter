# aws_db_proxy_target
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
module "aws_db_proxy_target" {
  source = "./modules/aws/r/aws_db_proxy_target"

  # db_cluster_identifier - (optional) is a type of string
  db_cluster_identifier = null
  # db_instance_identifier - (optional) is a type of string
  db_instance_identifier = null
  # db_proxy_name - (required) is a type of string
  db_proxy_name = null
  # target_group_name - (required) is a type of string
  target_group_name = null
}
```
[top](#index)
### Variables
```hcl
variable "db_cluster_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_instance_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_proxy_name" {
  description = "(required)"
  type        = string
}

variable "target_group_name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_db_proxy_target" "this" {
  db_cluster_identifier  = var.db_cluster_identifier
  db_instance_identifier = var.db_instance_identifier
  db_proxy_name          = var.db_proxy_name
  target_group_name      = var.target_group_name
}
```
[top](#index)
### Outputs
```hcl
output "endpoint" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.id
}

output "port" {
  description = "returns a number"
  value       = aws_db_proxy_target.this.port
}

output "rds_resource_id" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.rds_resource_id
}

output "target_arn" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.target_arn
}

output "tracked_cluster_id" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.tracked_cluster_id
}

output "type" {
  description = "returns a string"
  value       = aws_db_proxy_target.this.type
}

output "this" {
  value = aws_db_proxy_target.this
}
```
[top](#index)
