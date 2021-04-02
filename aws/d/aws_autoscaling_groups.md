# aws_autoscaling_groups

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
module "aws_autoscaling_groups" {
  source = "./modules/aws/d/aws_autoscaling_groups"


  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_autoscaling_groups" "this" {

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
output "arns" {
  description = "returns a list of string"
  value       = data.aws_autoscaling_groups.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_autoscaling_groups.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.aws_autoscaling_groups.this.names
}

output "this" {
  value = aws_autoscaling_groups.this
}
```

[top](#index)