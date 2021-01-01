# aws_elastic_beanstalk_configuration_template

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_elastic_beanstalk_configuration_template" {
  source = "./modules/aws/r/aws_elastic_beanstalk_configuration_template"

  # application - (required) is a type of string
  application = null
  # description - (optional) is a type of string
  description = null
  # environment_id - (optional) is a type of string
  environment_id = null
  # name - (required) is a type of string
  name = null
  # solution_stack_name - (optional) is a type of string
  solution_stack_name = null

  setting = [{
    name      = null
    namespace = null
    resource  = null
    value     = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "application" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "environment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "solution_stack_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "setting" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      namespace = string
      resource  = string
      value     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_elastic_beanstalk_configuration_template" "this" {
  application         = var.application
  description         = var.description
  environment_id      = var.environment_id
  name                = var.name
  solution_stack_name = var.solution_stack_name

  dynamic "setting" {
    for_each = var.setting
    content {
      name      = setting.value["name"]
      namespace = setting.value["namespace"]
      resource  = setting.value["resource"]
      value     = setting.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_elastic_beanstalk_configuration_template.this.id
}

output "this" {
  value = aws_elastic_beanstalk_configuration_template.this
}
```

[top](#index)