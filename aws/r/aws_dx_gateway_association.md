# aws_dx_gateway_association

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
module "aws_dx_gateway_association" {
  source = "./modules/aws/r/aws_dx_gateway_association"

  # allowed_prefixes - (optional) is a type of set of string
  allowed_prefixes = []
  # associated_gateway_id - (optional) is a type of string
  associated_gateway_id = null
  # associated_gateway_owner_account_id - (optional) is a type of string
  associated_gateway_owner_account_id = null
  # dx_gateway_id - (required) is a type of string
  dx_gateway_id = null
  # proposal_id - (optional) is a type of string
  proposal_id = null
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = null

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
variable "allowed_prefixes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "associated_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "associated_gateway_owner_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dx_gateway_id" {
  description = "(required)"
  type        = string
}

variable "proposal_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_gateway_id" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dx_gateway_association" "this" {
  # allowed_prefixes - (optional) is a type of set of string
  allowed_prefixes = var.allowed_prefixes
  # associated_gateway_id - (optional) is a type of string
  associated_gateway_id = var.associated_gateway_id
  # associated_gateway_owner_account_id - (optional) is a type of string
  associated_gateway_owner_account_id = var.associated_gateway_owner_account_id
  # dx_gateway_id - (required) is a type of string
  dx_gateway_id = var.dx_gateway_id
  # proposal_id - (optional) is a type of string
  proposal_id = var.proposal_id
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = var.vpn_gateway_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowed_prefixes" {
  description = "returns a set of string"
  value       = aws_dx_gateway_association.this.allowed_prefixes
}

output "associated_gateway_id" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.associated_gateway_id
}

output "associated_gateway_owner_account_id" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.associated_gateway_owner_account_id
}

output "associated_gateway_type" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.associated_gateway_type
}

output "dx_gateway_association_id" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.dx_gateway_association_id
}

output "dx_gateway_owner_account_id" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.dx_gateway_owner_account_id
}

output "id" {
  description = "returns a string"
  value       = aws_dx_gateway_association.this.id
}

output "this" {
  value = aws_dx_gateway_association.this
}
```

[top](#index)