# aws_devicefarm_project

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
module "aws_devicefarm_project" {
  source = "./modules/aws/r/aws_devicefarm_project"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_devicefarm_project" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_devicefarm_project.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_devicefarm_project.this.id
}

output "this" {
  value = aws_devicefarm_project.this
}
```

[top](#index)