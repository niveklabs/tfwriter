# aws_load_balancer_listener_policy

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
module "aws_load_balancer_listener_policy" {
  source = "./modules/aws/r/aws_load_balancer_listener_policy"

  # load_balancer_name - (required) is a type of string
  load_balancer_name = null
  # load_balancer_port - (required) is a type of number
  load_balancer_port = null
  # policy_names - (optional) is a type of set of string
  policy_names = []
}
```

[top](#index)

### Variables

```hcl
variable "load_balancer_name" {
  description = "(required)"
  type        = string
}

variable "load_balancer_port" {
  description = "(required)"
  type        = number
}

variable "policy_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_load_balancer_listener_policy" "this" {
  load_balancer_name = var.load_balancer_name
  load_balancer_port = var.load_balancer_port
  policy_names       = var.policy_names
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_load_balancer_listener_policy.this.id
}

output "this" {
  value = aws_load_balancer_listener_policy.this
}
```

[top](#index)