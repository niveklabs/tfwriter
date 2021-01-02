# aws_cloudtrail_service_account

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
module "aws_cloudtrail_service_account" {
  source = "./modules/aws/d/aws_cloudtrail_service_account"

  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_cloudtrail_service_account" "this" {
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_cloudtrail_service_account.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudtrail_service_account.this.id
}

output "this" {
  value = aws_cloudtrail_service_account.this
}
```

[top](#index)