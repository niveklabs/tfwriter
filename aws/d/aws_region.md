# aws_region

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
module "aws_region" {
  source = "./modules/aws/d/aws_region"

  # endpoint - (optional) is a type of string
  endpoint = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_region" "this" {
  endpoint = var.endpoint
  name     = var.name
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.aws_region.this.description
}

output "endpoint" {
  description = "returns a string"
  value       = data.aws_region.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.aws_region.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_region.this.name
}

output "this" {
  value = aws_region.this
}
```

[top](#index)