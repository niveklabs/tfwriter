# aws_directory_service_log_subscription

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_directory_service_log_subscription" {
  source = "./modules/aws/r/aws_directory_service_log_subscription"

  # directory_id - (required) is a type of string
  directory_id = null
  # log_group_name - (required) is a type of string
  log_group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "directory_id" {
  description = "(required)"
  type        = string
}

variable "log_group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_directory_service_log_subscription" "this" {
  directory_id   = var.directory_id
  log_group_name = var.log_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_directory_service_log_subscription.this.id
}

output "this" {
  value = aws_directory_service_log_subscription.this
}
```

[top](#index)