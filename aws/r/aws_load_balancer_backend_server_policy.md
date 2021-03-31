# aws_load_balancer_backend_server_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_load_balancer_backend_server_policy" {
  source = "./modules/aws/r/aws_load_balancer_backend_server_policy"

  # instance_port - (required) is a type of number
  instance_port = null
  # load_balancer_name - (required) is a type of string
  load_balancer_name = null
  # policy_names - (optional) is a type of set of string
  policy_names = []
}
```

[top](#index)

### Variables

```terraform
variable "instance_port" {
  description = "(required)"
  type        = number
}

variable "load_balancer_name" {
  description = "(required)"
  type        = string
}

variable "policy_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_load_balancer_backend_server_policy" "this" {
  instance_port      = var.instance_port
  load_balancer_name = var.load_balancer_name
  policy_names       = var.policy_names
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_load_balancer_backend_server_policy.this.id
}

output "this" {
  value = aws_load_balancer_backend_server_policy.this
}
```

[top](#index)