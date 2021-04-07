# aws_ami_ids

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ami_ids" {
  source = "./modules/aws/d/aws_ami_ids"

  # executable_users - (optional) is a type of list of string
  executable_users = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # owners - (required) is a type of list of string
  owners = []
  # sort_ascending - (optional) is a type of bool
  sort_ascending = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "executable_users" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owners" {
  description = "(required)"
  type        = list(string)
}

variable "sort_ascending" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ami_ids" "this" {
  # executable_users - (optional) is a type of list of string
  executable_users = var.executable_users
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # owners - (required) is a type of list of string
  owners = var.owners
  # sort_ascending - (optional) is a type of bool
  sort_ascending = var.sort_ascending

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_ami_ids.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.aws_ami_ids.this.ids
}

output "this" {
  value = aws_ami_ids.this
}
```

[top](#index)