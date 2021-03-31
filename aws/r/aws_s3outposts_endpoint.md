# aws_s3outposts_endpoint

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3outposts_endpoint" {
  source = "./modules/aws/r/aws_s3outposts_endpoint"

  # outpost_id - (required) is a type of string
  outpost_id = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "outpost_id" {
  description = "(required)"
  type        = string
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3outposts_endpoint" "this" {
  outpost_id        = var.outpost_id
  security_group_id = var.security_group_id
  subnet_id         = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_s3outposts_endpoint.this.arn
}

output "cidr_block" {
  description = "returns a string"
  value       = aws_s3outposts_endpoint.this.cidr_block
}

output "creation_time" {
  description = "returns a string"
  value       = aws_s3outposts_endpoint.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = aws_s3outposts_endpoint.this.id
}

output "network_interfaces" {
  description = "returns a set of object"
  value       = aws_s3outposts_endpoint.this.network_interfaces
}

output "this" {
  value = aws_s3outposts_endpoint.this
}
```

[top](#index)