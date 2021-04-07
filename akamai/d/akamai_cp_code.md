# akamai_cp_code

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_cp_code" {
  source = "./modules/akamai/d/akamai_cp_code"

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
```

[top](#index)

### Datasource

```terraform
data "akamai_cp_code" "this" {
  # contract - (optional) is a type of string
  contract = var.contract
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # group - (optional) is a type of string
  group = var.group
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "contract" {
  description = "returns a string"
  value       = data.akamai_cp_code.this.contract
}

output "contract_id" {
  description = "returns a string"
  value       = data.akamai_cp_code.this.contract_id
}

output "group" {
  description = "returns a string"
  value       = data.akamai_cp_code.this.group
}

output "group_id" {
  description = "returns a string"
  value       = data.akamai_cp_code.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.akamai_cp_code.this.id
}

output "product_ids" {
  description = "returns a list of string"
  value       = data.akamai_cp_code.this.product_ids
}

output "this" {
  value = akamai_cp_code.this
}
```

[top](#index)