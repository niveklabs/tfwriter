# aws_config_configuration_recorder_status

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_config_configuration_recorder_status" {
  source = "./modules/aws/r/aws_config_configuration_recorder_status"

  # is_enabled - (required) is a type of bool
  is_enabled = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "is_enabled" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_configuration_recorder_status" "this" {
  # is_enabled - (required) is a type of bool
  is_enabled = var.is_enabled
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_config_configuration_recorder_status.this.id
}

output "this" {
  value = aws_config_configuration_recorder_status.this
}
```

[top](#index)