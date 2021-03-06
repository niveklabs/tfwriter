# aws_codecommit_trigger

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
module "aws_codecommit_trigger" {
  source = "./modules/aws/r/aws_codecommit_trigger"

  # repository_name - (required) is a type of string
  repository_name = null

  trigger = [{
    branches        = []
    custom_data     = null
    destination_arn = null
    events          = []
    name            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "repository_name" {
  description = "(required)"
  type        = string
}

variable "trigger" {
  description = "nested block: NestingSet, min items: 1, max items: 10"
  type = set(object(
    {
      branches        = list(string)
      custom_data     = string
      destination_arn = string
      events          = list(string)
      name            = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_codecommit_trigger" "this" {
  # repository_name - (required) is a type of string
  repository_name = var.repository_name

  dynamic "trigger" {
    for_each = var.trigger
    content {
      # branches - (optional) is a type of list of string
      branches = trigger.value["branches"]
      # custom_data - (optional) is a type of string
      custom_data = trigger.value["custom_data"]
      # destination_arn - (required) is a type of string
      destination_arn = trigger.value["destination_arn"]
      # events - (required) is a type of list of string
      events = trigger.value["events"]
      # name - (required) is a type of string
      name = trigger.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "configuration_id" {
  description = "returns a string"
  value       = aws_codecommit_trigger.this.configuration_id
}

output "id" {
  description = "returns a string"
  value       = aws_codecommit_trigger.this.id
}

output "this" {
  value = aws_codecommit_trigger.this
}
```

[top](#index)