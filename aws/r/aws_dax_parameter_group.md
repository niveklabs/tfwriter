# aws_dax_parameter_group

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
module "aws_dax_parameter_group" {
  source = "./modules/aws/r/aws_dax_parameter_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  parameters = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_dax_parameter_group" "this" {
  description = var.description
  name        = var.name

  dynamic "parameters" {
    for_each = var.parameters
    content {
      name  = parameters.value["name"]
      value = parameters.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_dax_parameter_group.this.id
}

output "this" {
  value = aws_dax_parameter_group.this
}
```

[top](#index)