# aws_inspector_rules_packages

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
module "aws_inspector_rules_packages" {
  source = "./modules/aws/d/aws_inspector_rules_packages"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "aws_inspector_rules_packages" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "arns" {
  description = "returns a list of string"
  value       = data.aws_inspector_rules_packages.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_inspector_rules_packages.this.id
}

output "this" {
  value = aws_inspector_rules_packages.this
}
```

[top](#index)