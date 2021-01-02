# aws_ebs_default_kms_key

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
module "aws_ebs_default_kms_key" {
  source = "./modules/aws/d/aws_ebs_default_kms_key"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_ebs_default_kms_key" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_ebs_default_kms_key.this.id
}

output "key_arn" {
  description = "returns a string"
  value       = data.aws_ebs_default_kms_key.this.key_arn
}

output "this" {
  value = aws_ebs_default_kms_key.this
}
```

[top](#index)