# aws_billing_service_account

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
module "aws_billing_service_account" {
  source = "./modules/aws/d/aws_billing_service_account"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_billing_service_account" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_billing_service_account.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_billing_service_account.this.id
}

output "this" {
  value = aws_billing_service_account.this
}
```

[top](#index)