# aws_organizations_organizational_units

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
module "aws_organizations_organizational_units" {
  source = "./modules/aws/d/aws_organizations_organizational_units"

  # parent_id - (required) is a type of string
  parent_id = null
}
```

[top](#index)

### Variables

```terraform
variable "parent_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_organizations_organizational_units" "this" {
  parent_id = var.parent_id
}
```

[top](#index)

### Outputs

```terraform
output "children" {
  description = "returns a list of object"
  value       = data.aws_organizations_organizational_units.this.children
}

output "id" {
  description = "returns a string"
  value       = data.aws_organizations_organizational_units.this.id
}

output "this" {
  value = aws_organizations_organizational_units.this
}
```

[top](#index)