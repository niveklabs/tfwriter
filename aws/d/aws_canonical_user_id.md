# aws_canonical_user_id

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
module "aws_canonical_user_id" {
  source = "./modules/aws/d/aws_canonical_user_id"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_canonical_user_id" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.aws_canonical_user_id.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.aws_canonical_user_id.this.id
}

output "this" {
  value = aws_canonical_user_id.this
}
```

[top](#index)