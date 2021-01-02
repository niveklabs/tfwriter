# aws_config_configuration_recorder

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_config_configuration_recorder" {
  source = "./modules/aws/r/aws_config_configuration_recorder"

  # name - (optional) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null

  recording_group = [{
    all_supported                 = null
    include_global_resource_types = null
    resource_types                = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "recording_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      all_supported                 = bool
      include_global_resource_types = bool
      resource_types                = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_configuration_recorder" "this" {
  name     = var.name
  role_arn = var.role_arn

  dynamic "recording_group" {
    for_each = var.recording_group
    content {
      all_supported                 = recording_group.value["all_supported"]
      include_global_resource_types = recording_group.value["include_global_resource_types"]
      resource_types                = recording_group.value["resource_types"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_config_configuration_recorder.this.id
}

output "this" {
  value = aws_config_configuration_recorder.this
}
```

[top](#index)