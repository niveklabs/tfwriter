# aws_lb_listener

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lb_listener" {
  source = "./modules/aws/d/aws_lb_listener"

  # arn - (optional) is a type of string
  arn = null
  # load_balancer_arn - (optional) is a type of string
  load_balancer_arn = null
  # port - (optional) is a type of number
  port = null
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_lb_listener" "this" {
  arn               = var.arn
  load_balancer_arn = var.load_balancer_arn
  port              = var.port
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.arn
}

output "certificate_arn" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.certificate_arn
}

output "default_action" {
  description = "returns a list of object"
  value       = data.aws_lb_listener.this.default_action
}

output "id" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.id
}

output "load_balancer_arn" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.load_balancer_arn
}

output "port" {
  description = "returns a number"
  value       = data.aws_lb_listener.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.protocol
}

output "ssl_policy" {
  description = "returns a string"
  value       = data.aws_lb_listener.this.ssl_policy
}

output "this" {
  value = aws_lb_listener.this
}
```

[top](#index)