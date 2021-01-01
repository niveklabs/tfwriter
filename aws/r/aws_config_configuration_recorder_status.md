# aws_config_configuration_recorder_status

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

```hcl
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

```hcl
resource "aws_config_configuration_recorder_status" "this" {
  is_enabled = var.is_enabled
  name       = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_config_configuration_recorder_status.this.id
}

output "this" {
  value = aws_config_configuration_recorder_status.this
}
```

[top](#index)