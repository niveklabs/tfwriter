# akamai_cp_code

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_cp_code" {
  source = "./modules/akamai/r/akamai_cp_code"

  # contract - (optional) is a type of string
  contract = null
  # contract_id - (optional) is a type of string
  contract_id = null
  # group - (optional) is a type of string
  group = null
  # group_id - (optional) is a type of string
  group_id = null
  # name - (required) is a type of string
  name = null
  # product - (required) is a type of string
  product = null
}
```

[top](#index)

### Variables

```terraform
variable "contract" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "product" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_cp_code" "this" {
  contract    = var.contract
  contract_id = var.contract_id
  group       = var.group
  group_id    = var.group_id
  name        = var.name
  product     = var.product
}
```

[top](#index)

### Outputs

```terraform
output "contract" {
  description = "returns a string"
  value       = akamai_cp_code.this.contract
}

output "contract_id" {
  description = "returns a string"
  value       = akamai_cp_code.this.contract_id
}

output "group" {
  description = "returns a string"
  value       = akamai_cp_code.this.group
}

output "group_id" {
  description = "returns a string"
  value       = akamai_cp_code.this.group_id
}

output "id" {
  description = "returns a string"
  value       = akamai_cp_code.this.id
}

output "this" {
  value = akamai_cp_code.this
}
```

[top](#index)