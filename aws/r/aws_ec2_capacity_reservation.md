# aws_ec2_capacity_reservation

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_ec2_capacity_reservation" {
  source = "./modules/aws/r/aws_ec2_capacity_reservation"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = null
  # end_date - (optional) is a type of string
  end_date = null
  # end_date_type - (optional) is a type of string
  end_date_type = null
  # ephemeral_storage - (optional) is a type of bool
  ephemeral_storage = null
  # instance_count - (required) is a type of number
  instance_count = null
  # instance_match_criteria - (optional) is a type of string
  instance_match_criteria = null
  # instance_platform - (required) is a type of string
  instance_platform = null
  # instance_type - (required) is a type of string
  instance_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenancy - (optional) is a type of string
  tenancy = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
}

variable "ebs_optimized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_date_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ephemeral_storage" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_count" {
  description = "(required)"
  type        = number
}

variable "instance_match_criteria" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_platform" {
  description = "(required)"
  type        = string
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenancy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_capacity_reservation" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # ebs_optimized - (optional) is a type of bool
  ebs_optimized = var.ebs_optimized
  # end_date - (optional) is a type of string
  end_date = var.end_date
  # end_date_type - (optional) is a type of string
  end_date_type = var.end_date_type
  # ephemeral_storage - (optional) is a type of bool
  ephemeral_storage = var.ephemeral_storage
  # instance_count - (required) is a type of number
  instance_count = var.instance_count
  # instance_match_criteria - (optional) is a type of string
  instance_match_criteria = var.instance_match_criteria
  # instance_platform - (required) is a type of string
  instance_platform = var.instance_platform
  # instance_type - (required) is a type of string
  instance_type = var.instance_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tenancy - (optional) is a type of string
  tenancy = var.tenancy
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ec2_capacity_reservation.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_capacity_reservation.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_capacity_reservation.this.owner_id
}

output "this" {
  value = aws_ec2_capacity_reservation.this
}
```

[top](#index)