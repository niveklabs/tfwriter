# aws_networkfirewall_firewall

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
module "aws_networkfirewall_firewall" {
  source = "./modules/aws/r/aws_networkfirewall_firewall"

  # delete_protection - (optional) is a type of bool
  delete_protection = null
  # description - (optional) is a type of string
  description = null
  # firewall_policy_arn - (required) is a type of string
  firewall_policy_arn = null
  # firewall_policy_change_protection - (optional) is a type of bool
  firewall_policy_change_protection = null
  # name - (required) is a type of string
  name = null
  # subnet_change_protection - (optional) is a type of bool
  subnet_change_protection = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  subnet_mapping = [{
    subnet_id = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "delete_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_policy_arn" {
  description = "(required)"
  type        = string
}

variable "firewall_policy_change_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "subnet_change_protection" {
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
  description = "(required)"
  type        = string
}

variable "subnet_mapping" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      subnet_id = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_networkfirewall_firewall" "this" {
  delete_protection                 = var.delete_protection
  description                       = var.description
  firewall_policy_arn               = var.firewall_policy_arn
  firewall_policy_change_protection = var.firewall_policy_change_protection
  name                              = var.name
  subnet_change_protection          = var.subnet_change_protection
  tags                              = var.tags
  vpc_id                            = var.vpc_id

  dynamic "subnet_mapping" {
    for_each = var.subnet_mapping
    content {
      subnet_id = subnet_mapping.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall.this.arn
}

output "firewall_status" {
  description = "returns a list of object"
  value       = aws_networkfirewall_firewall.this.firewall_status
}

output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall.this.id
}

output "update_token" {
  description = "returns a string"
  value       = aws_networkfirewall_firewall.this.update_token
}

output "this" {
  value = aws_networkfirewall_firewall.this
}
```

[top](#index)