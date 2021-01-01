# aws_cloud9_environment_ec2

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
module "aws_cloud9_environment_ec2" {
  source = "./modules/aws/r/aws_cloud9_environment_ec2"

  # automatic_stop_time_minutes - (optional) is a type of number
  automatic_stop_time_minutes = null
  # description - (optional) is a type of string
  description = null
  # instance_type - (required) is a type of string
  instance_type = null
  # name - (required) is a type of string
  name = null
  # owner_arn - (optional) is a type of string
  owner_arn = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "automatic_stop_time_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
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
resource "aws_cloud9_environment_ec2" "this" {
  automatic_stop_time_minutes = var.automatic_stop_time_minutes
  description                 = var.description
  instance_type               = var.instance_type
  name                        = var.name
  owner_arn                   = var.owner_arn
  subnet_id                   = var.subnet_id
  tags                        = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_cloud9_environment_ec2.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloud9_environment_ec2.this.id
}

output "owner_arn" {
  description = "returns a string"
  value       = aws_cloud9_environment_ec2.this.owner_arn
}

output "type" {
  description = "returns a string"
  value       = aws_cloud9_environment_ec2.this.type
}

output "this" {
  value = aws_cloud9_environment_ec2.this
}
```

[top](#index)