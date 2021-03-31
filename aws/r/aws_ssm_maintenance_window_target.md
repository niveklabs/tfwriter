# aws_ssm_maintenance_window_target

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
module "aws_ssm_maintenance_window_target" {
  source = "./modules/aws/r/aws_ssm_maintenance_window_target"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # owner_information - (optional) is a type of string
  owner_information = null
  # resource_type - (required) is a type of string
  resource_type = null
  # window_id - (required) is a type of string
  window_id = null

  targets = [{
    key    = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_information" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_type" {
  description = "(required)"
  type        = string
}

variable "window_id" {
  description = "(required)"
  type        = string
}

variable "targets" {
  description = "nested block: NestingList, min items: 1, max items: 5"
  type = set(object(
    {
      key    = string
      values = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_maintenance_window_target" "this" {
  description       = var.description
  name              = var.name
  owner_information = var.owner_information
  resource_type     = var.resource_type
  window_id         = var.window_id

  dynamic "targets" {
    for_each = var.targets
    content {
      key    = targets.value["key"]
      values = targets.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_maintenance_window_target.this.id
}

output "this" {
  value = aws_ssm_maintenance_window_target.this
}
```

[top](#index)