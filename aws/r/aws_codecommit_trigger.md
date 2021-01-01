# aws_codecommit_trigger

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

```hcl
variable "repository_name" {
  description = "(required)"
  type        = string
}

variable "trigger" {
  description = "nested mode: NestingSet, min items: 1, max items: 10"
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

```hcl
resource "aws_codecommit_trigger" "this" {
  repository_name = var.repository_name

  dynamic "trigger" {
    for_each = var.trigger
    content {
      branches        = trigger.value["branches"]
      custom_data     = trigger.value["custom_data"]
      destination_arn = trigger.value["destination_arn"]
      events          = trigger.value["events"]
      name            = trigger.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
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