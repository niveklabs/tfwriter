# aws_db_proxy

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
module "aws_db_proxy" {
  source = "./modules/aws/r/aws_db_proxy"

  # debug_logging - (optional) is a type of bool
  debug_logging = null
  # engine_family - (required) is a type of string
  engine_family = null
  # idle_client_timeout - (optional) is a type of number
  idle_client_timeout = null
  # name - (required) is a type of string
  name = null
  # require_tls - (optional) is a type of bool
  require_tls = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []
  # vpc_subnet_ids - (required) is a type of set of string
  vpc_subnet_ids = []

  auth = [{
    auth_scheme = null
    description = null
    iam_auth    = null
    secret_arn  = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "debug_logging" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "engine_family" {
  description = "(required)"
  type        = string
}

variable "idle_client_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "require_tls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vpc_subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "auth" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      auth_scheme = string
      description = string
      iam_auth    = string
      secret_arn  = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_db_proxy" "this" {
  debug_logging          = var.debug_logging
  engine_family          = var.engine_family
  idle_client_timeout    = var.idle_client_timeout
  name                   = var.name
  require_tls            = var.require_tls
  role_arn               = var.role_arn
  tags                   = var.tags
  vpc_security_group_ids = var.vpc_security_group_ids
  vpc_subnet_ids         = var.vpc_subnet_ids

  dynamic "auth" {
    for_each = var.auth
    content {
      auth_scheme = auth.value["auth_scheme"]
      description = auth.value["description"]
      iam_auth    = auth.value["iam_auth"]
      secret_arn  = auth.value["secret_arn"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_db_proxy.this.arn
}

output "endpoint" {
  description = "returns a string"
  value       = aws_db_proxy.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_db_proxy.this.id
}

output "idle_client_timeout" {
  description = "returns a number"
  value       = aws_db_proxy.this.idle_client_timeout
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_db_proxy.this.vpc_security_group_ids
}

output "this" {
  value = aws_db_proxy.this
}
```

[top](#index)