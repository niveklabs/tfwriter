# aws_ssm_patch_baseline

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
module "aws_ssm_patch_baseline" {
  source = "./modules/aws/d/aws_ssm_patch_baseline"

  # default_baseline - (optional) is a type of bool
  default_baseline = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # operating_system - (optional) is a type of string
  operating_system = null
  # owner - (required) is a type of string
  owner = null
}
```

[top](#index)

### Variables

```terraform
variable "default_baseline" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operating_system" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_ssm_patch_baseline" "this" {
  default_baseline = var.default_baseline
  name_prefix      = var.name_prefix
  operating_system = var.operating_system
  owner            = var.owner
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aws_ssm_patch_baseline.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_ssm_patch_baseline.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_ssm_patch_baseline.this.name
}

output "this" {
  value = aws_ssm_patch_baseline.this
}
```

[top](#index)