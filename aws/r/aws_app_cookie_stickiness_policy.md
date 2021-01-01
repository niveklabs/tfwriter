# aws_app_cookie_stickiness_policy

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
module "aws_app_cookie_stickiness_policy" {
  source = "./modules/aws/r/aws_app_cookie_stickiness_policy"

  # cookie_name - (required) is a type of string
  cookie_name = null
  # lb_port - (required) is a type of number
  lb_port = null
  # load_balancer - (required) is a type of string
  load_balancer = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "cookie_name" {
  description = "(required)"
  type        = string
}

variable "lb_port" {
  description = "(required)"
  type        = number
}

variable "load_balancer" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_app_cookie_stickiness_policy" "this" {
  cookie_name   = var.cookie_name
  lb_port       = var.lb_port
  load_balancer = var.load_balancer
  name          = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_app_cookie_stickiness_policy.this.id
}

output "this" {
  value = aws_app_cookie_stickiness_policy.this
}
```

[top](#index)