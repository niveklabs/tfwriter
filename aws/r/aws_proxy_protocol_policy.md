# aws_proxy_protocol_policy

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
module "aws_proxy_protocol_policy" {
  source = "./modules/aws/r/aws_proxy_protocol_policy"

  # instance_ports - (required) is a type of set of string
  instance_ports = []
  # load_balancer - (required) is a type of string
  load_balancer = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_ports" {
  description = "(required)"
  type        = set(string)
}

variable "load_balancer" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_proxy_protocol_policy" "this" {
  # instance_ports - (required) is a type of set of string
  instance_ports = var.instance_ports
  # load_balancer - (required) is a type of string
  load_balancer = var.load_balancer
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_proxy_protocol_policy.this.id
}

output "this" {
  value = aws_proxy_protocol_policy.this
}
```

[top](#index)