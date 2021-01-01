# aws_ec2_tag

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
module "aws_ec2_tag" {
  source = "./modules/aws/r/aws_ec2_tag"

  # key - (required) is a type of string
  key = null
  # resource_id - (required) is a type of string
  resource_id = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```hcl
variable "key" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ec2_tag" "this" {
  key         = var.key
  resource_id = var.resource_id
  value       = var.value
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ec2_tag.this.id
}

output "this" {
  value = aws_ec2_tag.this
}
```

[top](#index)