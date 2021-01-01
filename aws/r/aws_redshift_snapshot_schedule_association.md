# aws_redshift_snapshot_schedule_association
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
module "aws_redshift_snapshot_schedule_association" {
  source = "./modules/aws/r/aws_redshift_snapshot_schedule_association"

  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # schedule_identifier - (required) is a type of string
  schedule_identifier = null
}
```
[top](#index)
### Variables
```hcl
variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "schedule_identifier" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_redshift_snapshot_schedule_association" "this" {
  cluster_identifier  = var.cluster_identifier
  schedule_identifier = var.schedule_identifier
}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_redshift_snapshot_schedule_association.this.id
}

output "this" {
  value = aws_redshift_snapshot_schedule_association.this
}
```
[top](#index)
