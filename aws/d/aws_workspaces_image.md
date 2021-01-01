# aws_workspaces_image

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
module "aws_workspaces_image" {
  source = "./modules/aws/d/aws_workspaces_image"

  # image_id - (required) is a type of string
  image_id = null
}
```

[top](#index)

### Variables

```hcl
variable "image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_workspaces_image" "this" {
  image_id = var.image_id
}
```

[top](#index)

### Outputs

```hcl
output "description" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.name
}

output "operating_system_type" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.operating_system_type
}

output "required_tenancy" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.required_tenancy
}

output "state" {
  description = "returns a string"
  value       = data.aws_workspaces_image.this.state
}

output "this" {
  value = aws_workspaces_image.this
}
```

[top](#index)