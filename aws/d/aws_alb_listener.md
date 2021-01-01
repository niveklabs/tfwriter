# aws_alb_listener

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
module "aws_alb_listener" {
  source = "./modules/aws/d/aws_alb_listener"

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

```hcl
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

```hcl
data "aws_alb_listener" "this" {
  arn               = var.arn
  load_balancer_arn = var.load_balancer_arn
  port              = var.port
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.arn
}

output "certificate_arn" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.certificate_arn
}

output "default_action" {
  description = "returns a list of object"
  value       = data.aws_alb_listener.this.default_action
}

output "id" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.id
}

output "load_balancer_arn" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.load_balancer_arn
}

output "port" {
  description = "returns a number"
  value       = data.aws_alb_listener.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.protocol
}

output "ssl_policy" {
  description = "returns a string"
  value       = data.aws_alb_listener.this.ssl_policy
}

output "this" {
  value = aws_alb_listener.this
}
```

[top](#index)