# aws_cloudhsm_v2_cluster
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
module "aws_cloudhsm_v2_cluster" {
  source = "./modules/aws/r/aws_cloudhsm_v2_cluster"

  # hsm_type - (required) is a type of string
  hsm_type = null
  # source_backup_identifier - (optional) is a type of string
  source_backup_identifier = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "hsm_type" {
  description = "(required)"
  type        = string
}

variable "source_backup_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_cloudhsm_v2_cluster" "this" {
  hsm_type                 = var.hsm_type
  source_backup_identifier = var.source_backup_identifier
  subnet_ids               = var.subnet_ids
  tags                     = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "cluster_certificates" {
  description = "returns a list of object"
  value       = aws_cloudhsm_v2_cluster.this.cluster_certificates
}

output "cluster_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_cluster.this.cluster_id
}

output "cluster_state" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_cluster.this.cluster_state
}

output "id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_cluster.this.id
}

output "security_group_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_cluster.this.security_group_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_cloudhsm_v2_cluster.this.vpc_id
}

output "this" {
  value = aws_cloudhsm_v2_cluster.this
}
```
[top](#index)
