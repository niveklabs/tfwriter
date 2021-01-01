# aws_outposts_outpost

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
module "aws_outposts_outpost" {
  source = "./modules/aws/d/aws_outposts_outpost"

  # arn - (optional) is a type of string
  arn = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "arn" {
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
data "aws_outposts_outpost" "this" {
  arn  = var.arn
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.availability_zone
}

output "availability_zone_id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.availability_zone_id
}

output "description" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.name
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.owner_id
}

output "site_id" {
  description = "returns a string"
  value       = data.aws_outposts_outpost.this.site_id
}

output "this" {
  value = aws_outposts_outpost.this
}
```

[top](#index)