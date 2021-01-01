# aws_dx_gateway_association_proposal

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
module "aws_dx_gateway_association_proposal" {
  source = "./modules/aws/r/aws_dx_gateway_association_proposal"

  # allowed_prefixes - (optional) is a type of set of string
  allowed_prefixes = []
  # associated_gateway_id - (required) is a type of string
  associated_gateway_id = null
  # dx_gateway_id - (required) is a type of string
  dx_gateway_id = null
  # dx_gateway_owner_account_id - (required) is a type of string
  dx_gateway_owner_account_id = null
}
```

[top](#index)

### Variables

```hcl
variable "allowed_prefixes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "associated_gateway_id" {
  description = "(required)"
  type        = string
}

variable "dx_gateway_id" {
  description = "(required)"
  type        = string
}

variable "dx_gateway_owner_account_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_dx_gateway_association_proposal" "this" {
  allowed_prefixes            = var.allowed_prefixes
  associated_gateway_id       = var.associated_gateway_id
  dx_gateway_id               = var.dx_gateway_id
  dx_gateway_owner_account_id = var.dx_gateway_owner_account_id
}
```

[top](#index)

### Outputs

```hcl
output "allowed_prefixes" {
  description = "returns a set of string"
  value       = aws_dx_gateway_association_proposal.this.allowed_prefixes
}

output "associated_gateway_owner_account_id" {
  description = "returns a string"
  value       = aws_dx_gateway_association_proposal.this.associated_gateway_owner_account_id
}

output "associated_gateway_type" {
  description = "returns a string"
  value       = aws_dx_gateway_association_proposal.this.associated_gateway_type
}

output "id" {
  description = "returns a string"
  value       = aws_dx_gateway_association_proposal.this.id
}

output "this" {
  value = aws_dx_gateway_association_proposal.this
}
```

[top](#index)