# datadog_integration_aws_lambda_arn

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_aws_lambda_arn" {
  source = "./modules/datadog/r/datadog_integration_aws_lambda_arn"

  # account_id - (required) is a type of string
  account_id = null
  # lambda_arn - (required) is a type of string
  lambda_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required) - Your AWS Account ID without dashes."
  type        = string
}

variable "lambda_arn" {
  description = "(required) - The ARN of the Datadog forwarder Lambda."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_aws_lambda_arn" "this" {
  account_id = var.account_id
  lambda_arn = var.lambda_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_aws_lambda_arn.this.id
}

output "this" {
  value = datadog_integration_aws_lambda_arn.this
}
```

[top](#index)