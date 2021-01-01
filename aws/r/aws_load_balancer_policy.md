# aws_load_balancer_policy

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
module "aws_load_balancer_policy" {
  source = "./modules/aws/r/aws_load_balancer_policy"

  # load_balancer_name - (required) is a type of string
  load_balancer_name = null
  # policy_name - (required) is a type of string
  policy_name = null
  # policy_type_name - (required) is a type of string
  policy_type_name = null

  policy_attribute = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "load_balancer_name" {
  description = "(required)"
  type        = string
}

variable "policy_name" {
  description = "(required)"
  type        = string
}

variable "policy_type_name" {
  description = "(required)"
  type        = string
}

variable "policy_attribute" {
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
resource "aws_load_balancer_policy" "this" {
  load_balancer_name = var.load_balancer_name
  policy_name        = var.policy_name
  policy_type_name   = var.policy_type_name

  dynamic "policy_attribute" {
    for_each = var.policy_attribute
    content {
      name  = policy_attribute.value["name"]
      value = policy_attribute.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_load_balancer_policy.this.id
}

output "this" {
  value = aws_load_balancer_policy.this
}
```

[top](#index)