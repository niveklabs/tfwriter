# aws_ec2_availability_zone_group

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
module "aws_ec2_availability_zone_group" {
  source = "./modules/aws/r/aws_ec2_availability_zone_group"

  # group_name - (required) is a type of string
  group_name = null
  # opt_in_status - (required) is a type of string
  opt_in_status = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required)"
  type        = string
}

variable "opt_in_status" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ec2_availability_zone_group" "this" {
  group_name    = var.group_name
  opt_in_status = var.opt_in_status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ec2_availability_zone_group.this.id
}

output "this" {
  value = aws_ec2_availability_zone_group.this
}
```

[top](#index)