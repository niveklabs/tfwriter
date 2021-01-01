# aws_ebs_snapshot
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
module "aws_ebs_snapshot" {
  source = "./modules/aws/r/aws_ebs_snapshot"

  # description - (optional) is a type of string
  description = null
  # tags - (optional) is a type of map of string
  tags = {}
  # volume_id - (required) is a type of string
  volume_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "volume_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_ebs_snapshot" "this" {
  description = var.description
  tags        = var.tags
  volume_id   = var.volume_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.arn
}

output "data_encryption_key_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.data_encryption_key_id
}

output "encrypted" {
  description = "returns a bool"
  value       = aws_ebs_snapshot.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.kms_key_id
}

output "owner_alias" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.owner_alias
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot.this.owner_id
}

output "volume_size" {
  description = "returns a number"
  value       = aws_ebs_snapshot.this.volume_size
}

output "this" {
  value = aws_ebs_snapshot.this
}
```
[top](#index)
