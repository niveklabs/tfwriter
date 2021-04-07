# aws_outposts_outpost_instance_type

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_outposts_outpost_instance_type" {
  source = "./modules/aws/d/aws_outposts_outpost_instance_type"

  # arn - (required) is a type of string
  arn = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # preferred_instance_types - (optional) is a type of list of string
  preferred_instance_types = []
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_instance_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_outposts_outpost_instance_type" "this" {
  # arn - (required) is a type of string
  arn = var.arn
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # preferred_instance_types - (optional) is a type of list of string
  preferred_instance_types = var.preferred_instance_types
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost_instance_type.this.id
}

output "instance_type" {
  description = "returns a string"
  value       = data.aws_outposts_outpost_instance_type.this.instance_type
}

output "this" {
  value = aws_outposts_outpost_instance_type.this
}
```

[top](#index)