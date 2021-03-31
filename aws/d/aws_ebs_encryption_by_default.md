# aws_ebs_encryption_by_default

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ebs_encryption_by_default" {
  source = "./modules/aws/d/aws_ebs_encryption_by_default"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_ebs_encryption_by_default" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.aws_ebs_encryption_by_default.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.aws_ebs_encryption_by_default.this.id
}

output "this" {
  value = aws_ebs_encryption_by_default.this
}
```

[top](#index)