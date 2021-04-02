# aws_instances

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
module "aws_instances" {
  source = "./modules/aws/d/aws_instances"

  # instance_state_names - (optional) is a type of set of string
  instance_state_names = []
  # instance_tags - (optional) is a type of map of string
  instance_tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_state_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "instance_tags" {
  description = "(optional)"
  type        = map(string)
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
data "aws_instances" "this" {
  instance_state_names = var.instance_state_names
  instance_tags        = var.instance_tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
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
  value       = data.aws_instances.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.aws_instances.this.ids
}

output "instance_tags" {
  description = "returns a map of string"
  value       = data.aws_instances.this.instance_tags
}

output "private_ips" {
  description = "returns a list of string"
  value       = data.aws_instances.this.private_ips
}

output "public_ips" {
  description = "returns a list of string"
  value       = data.aws_instances.this.public_ips
}

output "this" {
  value = aws_instances.this
}
```

[top](#index)