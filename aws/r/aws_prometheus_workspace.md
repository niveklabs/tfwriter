# aws_prometheus_workspace

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
module "aws_prometheus_workspace" {
  source = "./modules/aws/r/aws_prometheus_workspace"

  # alias - (optional) is a type of string
  alias = null
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_prometheus_workspace" "this" {
  alias = var.alias
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_prometheus_workspace.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_prometheus_workspace.this.id
}

output "prometheus_endpoint" {
  description = "returns a string"
  value       = aws_prometheus_workspace.this.prometheus_endpoint
}

output "this" {
  value = aws_prometheus_workspace.this
}
```

[top](#index)