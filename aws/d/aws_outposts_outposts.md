# aws_outposts_outposts

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
module "aws_outposts_outposts" {
  source = "./modules/aws/d/aws_outposts_outposts"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # availability_zone_id - (optional) is a type of string
  availability_zone_id = null
  # site_id - (optional) is a type of string
  site_id = null
}
```

[top](#index)

### Variables

```hcl
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "site_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_outposts_outposts" "this" {
  availability_zone    = var.availability_zone
  availability_zone_id = var.availability_zone_id
  site_id              = var.site_id
}
```

[top](#index)

### Outputs

```hcl
output "arns" {
  description = "returns a set of string"
  value       = data.aws_outposts_outposts.this.arns
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_outposts_outposts.this.availability_zone
}

output "availability_zone_id" {
  description = "returns a string"
  value       = data.aws_outposts_outposts.this.availability_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_outposts_outposts.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_outposts_outposts.this.ids
}

output "site_id" {
  description = "returns a string"
  value       = data.aws_outposts_outposts.this.site_id
}

output "this" {
  value = aws_outposts_outposts.this
}
```

[top](#index)