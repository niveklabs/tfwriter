# aws_outposts_outpost_instance_types

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_outposts_outpost_instance_types" {
  source = "./modules/aws/d/aws_outposts_outpost_instance_types"

  # arn - (required) is a type of string
  arn = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_outposts_outpost_instance_types" "this" {
  arn = var.arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost_instance_types.this.id
}

output "instance_types" {
  description = "returns a set of string"
  value       = data.aws_outposts_outpost_instance_types.this.instance_types
}

output "this" {
  value = aws_outposts_outpost_instance_types.this
}
```

[top](#index)