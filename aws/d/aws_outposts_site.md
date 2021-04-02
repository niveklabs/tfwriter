# aws_outposts_site

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
module "aws_outposts_site" {
  source = "./modules/aws/d/aws_outposts_site"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_outposts_site" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.aws_outposts_site.this.account_id
}

output "description" {
  description = "returns a string"
  value       = data.aws_outposts_site.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_outposts_site.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_outposts_site.this.name
}

output "this" {
  value = aws_outposts_site.this
}
```

[top](#index)