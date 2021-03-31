# aws_dx_lag

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
module "aws_dx_lag" {
  source = "./modules/aws/r/aws_dx_lag"

  # connections_bandwidth - (required) is a type of string
  connections_bandwidth = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "connections_bandwidth" {
  description = "(required)"
  type        = string
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_dx_lag" "this" {
  connections_bandwidth = var.connections_bandwidth
  force_destroy         = var.force_destroy
  location              = var.location
  name                  = var.name
  tags                  = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_dx_lag.this.arn
}

output "has_logical_redundancy" {
  description = "returns a string"
  value       = aws_dx_lag.this.has_logical_redundancy
}

output "id" {
  description = "returns a string"
  value       = aws_dx_lag.this.id
}

output "jumbo_frame_capable" {
  description = "returns a bool"
  value       = aws_dx_lag.this.jumbo_frame_capable
}

output "this" {
  value = aws_dx_lag.this
}
```

[top](#index)