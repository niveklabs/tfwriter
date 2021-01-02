# aws_datasync_agent

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_datasync_agent" {
  source = "./modules/aws/r/aws_datasync_agent"

  # activation_key - (optional) is a type of string
  activation_key = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activation_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_datasync_agent" "this" {
  activation_key = var.activation_key
  ip_address     = var.ip_address
  name           = var.name
  tags           = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "activation_key" {
  description = "returns a string"
  value       = aws_datasync_agent.this.activation_key
}

output "arn" {
  description = "returns a string"
  value       = aws_datasync_agent.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_agent.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_datasync_agent.this.ip_address
}

output "this" {
  value = aws_datasync_agent.this
}
```

[top](#index)