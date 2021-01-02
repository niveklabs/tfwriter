# aws_workspaces_bundle

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_workspaces_bundle" {
  source = "./modules/aws/d/aws_workspaces_bundle"

  # bundle_id - (optional) is a type of string
  bundle_id = null
  # name - (optional) is a type of string
  name = null
  # owner - (optional) is a type of string
  owner = null
}
```

[top](#index)

### Variables

```terraform
variable "bundle_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_workspaces_bundle" "this" {
  bundle_id = var.bundle_id
  name      = var.name
  owner     = var.owner
}
```

[top](#index)

### Outputs

```terraform
output "compute_type" {
  description = "returns a list of object"
  value       = data.aws_workspaces_bundle.this.compute_type
}

output "description" {
  description = "returns a string"
  value       = data.aws_workspaces_bundle.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_workspaces_bundle.this.id
}

output "root_storage" {
  description = "returns a list of object"
  value       = data.aws_workspaces_bundle.this.root_storage
}

output "user_storage" {
  description = "returns a list of object"
  value       = data.aws_workspaces_bundle.this.user_storage
}

output "this" {
  value = aws_workspaces_bundle.this
}
```

[top](#index)