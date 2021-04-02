# aws_security_group

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
module "aws_security_group" {
  source = "./modules/aws/r/aws_security_group"

  # description - (optional) is a type of string
  description = null
  # egress - (optional) is a type of set of object
  egress = [{
    cidr_blocks      = []
    description      = null
    from_port        = null
    ipv6_cidr_blocks = []
    prefix_list_ids  = []
    protocol         = null
    security_groups  = []
    self             = null
    to_port          = null
  }]
  # ingress - (optional) is a type of set of object
  ingress = [{
    cidr_blocks      = []
    description      = null
    from_port        = null
    ipv6_cidr_blocks = []
    prefix_list_ids  = []
    protocol         = null
    security_groups  = []
    self             = null
    to_port          = null
  }]
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # revoke_rules_on_delete - (optional) is a type of bool
  revoke_rules_on_delete = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "egress" {
  description = "(optional)"
  type = set(object(
    {
      cidr_blocks      = list(string)
      description      = string
      from_port        = number
      ipv6_cidr_blocks = list(string)
      prefix_list_ids  = list(string)
      protocol         = string
      security_groups  = set(string)
      self             = bool
      to_port          = number
    }
  ))
  default = null
}

variable "ingress" {
  description = "(optional)"
  type = set(object(
    {
      cidr_blocks      = list(string)
      description      = string
      from_port        = number
      ipv6_cidr_blocks = list(string)
      prefix_list_ids  = list(string)
      protocol         = string
      security_groups  = set(string)
      self             = bool
      to_port          = number
    }
  ))
  default = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "revoke_rules_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_security_group" "this" {
  description            = var.description
  egress                 = var.egress
  ingress                = var.ingress
  name                   = var.name
  name_prefix            = var.name_prefix
  revoke_rules_on_delete = var.revoke_rules_on_delete
  tags                   = var.tags
  vpc_id                 = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_security_group.this.arn
}

output "egress" {
  description = "returns a set of object"
  value       = aws_security_group.this.egress
}

output "id" {
  description = "returns a string"
  value       = aws_security_group.this.id
}

output "ingress" {
  description = "returns a set of object"
  value       = aws_security_group.this.ingress
}

output "name" {
  description = "returns a string"
  value       = aws_security_group.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = aws_security_group.this.name_prefix
}

output "owner_id" {
  description = "returns a string"
  value       = aws_security_group.this.owner_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_security_group.this.vpc_id
}

output "this" {
  value = aws_security_group.this
}
```

[top](#index)