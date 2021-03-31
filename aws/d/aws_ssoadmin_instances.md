# aws_ssoadmin_instances

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
module "aws_ssoadmin_instances" {
  source = "./modules/aws/d/aws_ssoadmin_instances"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_ssoadmin_instances" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "arns" {
  description = "returns a set of string"
  value       = data.aws_ssoadmin_instances.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_ssoadmin_instances.this.id
}

output "identity_store_ids" {
  description = "returns a set of string"
  value       = data.aws_ssoadmin_instances.this.identity_store_ids
}

output "this" {
  value = aws_ssoadmin_instances.this
}
```

[top](#index)