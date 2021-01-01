# aws_eks_cluster
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
module "aws_eks_cluster" {
  source = "./modules/aws/d/aws_eks_cluster"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```
[top](#index)
### Variables
```hcl
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

### Datasource
```hcl
data "aws_eks_cluster" "this" {
  name = var.name
  tags = var.tags
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.arn
}

output "certificate_authority" {
  description = "returns a list of object"
  value       = data.aws_eks_cluster.this.certificate_authority
}

output "created_at" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.created_at
}

output "enabled_cluster_log_types" {
  description = "returns a set of string"
  value       = data.aws_eks_cluster.this.enabled_cluster_log_types
}

output "endpoint" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.aws_eks_cluster.this.identity
}

output "kubernetes_network_config" {
  description = "returns a list of object"
  value       = data.aws_eks_cluster.this.kubernetes_network_config
}

output "platform_version" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.platform_version
}

output "role_arn" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.role_arn
}

output "status" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_eks_cluster.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_eks_cluster.this.version
}

output "vpc_config" {
  description = "returns a list of object"
  value       = data.aws_eks_cluster.this.vpc_config
}

output "this" {
  value = aws_eks_cluster.this
}
```
[top](#index)
