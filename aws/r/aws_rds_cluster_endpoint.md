# aws_rds_cluster_endpoint
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
module "aws_rds_cluster_endpoint" {
  source = "./modules/aws/r/aws_rds_cluster_endpoint"

  # cluster_endpoint_identifier - (required) is a type of string
  cluster_endpoint_identifier = null
  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # custom_endpoint_type - (required) is a type of string
  custom_endpoint_type = null
  # excluded_members - (optional) is a type of set of string
  excluded_members = []
  # static_members - (optional) is a type of set of string
  static_members = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
variable "cluster_endpoint_identifier" {
  description = "(required)"
  type        = string
}

variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "custom_endpoint_type" {
  description = "(required)"
  type        = string
}

variable "excluded_members" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "static_members" {
  description = "(optional)"
  type        = set(string)
  default     = null
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
resource "aws_rds_cluster_endpoint" "this" {
  cluster_endpoint_identifier = var.cluster_endpoint_identifier
  cluster_identifier          = var.cluster_identifier
  custom_endpoint_type        = var.custom_endpoint_type
  excluded_members            = var.excluded_members
  static_members              = var.static_members
  tags                        = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_rds_cluster_endpoint.this.arn
}

output "endpoint" {
  description = "returns a string"
  value       = aws_rds_cluster_endpoint.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_rds_cluster_endpoint.this.id
}

output "this" {
  value = aws_rds_cluster_endpoint.this
}
```
[top](#index)
