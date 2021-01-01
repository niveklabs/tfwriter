# aws_lakeformation_resource

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
module "aws_lakeformation_resource" {
  source = "./modules/aws/r/aws_lakeformation_resource"

  # arn - (required) is a type of string
  arn = null
  # role_arn - (optional) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "arn" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_lakeformation_resource" "this" {
  arn      = var.arn
  role_arn = var.role_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_lakeformation_resource.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = aws_lakeformation_resource.this.last_modified
}

output "role_arn" {
  description = "returns a string"
  value       = aws_lakeformation_resource.this.role_arn
}

output "this" {
  value = aws_lakeformation_resource.this
}
```

[top](#index)