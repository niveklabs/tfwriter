# aws_transfer_user

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
module "aws_transfer_user" {
  source = "./modules/aws/r/aws_transfer_user"

  # home_directory - (optional) is a type of string
  home_directory = null
  # home_directory_type - (optional) is a type of string
  home_directory_type = null
  # policy - (optional) is a type of string
  policy = null
  # role - (required) is a type of string
  role = null
  # server_id - (required) is a type of string
  server_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_name - (required) is a type of string
  user_name = null

  home_directory_mappings = [{
    entry  = null
    target = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "home_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "home_directory_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_name" {
  description = "(required)"
  type        = string
}

variable "home_directory_mappings" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      entry  = string
      target = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_transfer_user" "this" {
  home_directory      = var.home_directory
  home_directory_type = var.home_directory_type
  policy              = var.policy
  role                = var.role
  server_id           = var.server_id
  tags                = var.tags
  user_name           = var.user_name

  dynamic "home_directory_mappings" {
    for_each = var.home_directory_mappings
    content {
      entry  = home_directory_mappings.value["entry"]
      target = home_directory_mappings.value["target"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_transfer_user.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_transfer_user.this.id
}

output "this" {
  value = aws_transfer_user.this
}
```

[top](#index)