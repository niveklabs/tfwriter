# akamai_group

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
module "akamai_group" {
  source = "./modules/akamai/d/akamai_group"

  # contract - (optional) is a type of string
  contract = null
  # contract_id - (optional) is a type of string
  contract_id = null
  # group_name - (optional) is a type of string
  group_name = null
  # name - (optional) is a type of string
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

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_group" "this" {
  # contract - (optional) is a type of string
  contract = var.contract
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # group_name - (optional) is a type of string
  group_name = var.group_name
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "contract" {
  description = "returns a string"
  value       = data.akamai_group.this.contract
}

output "contract_id" {
  description = "returns a string"
  value       = data.akamai_group.this.contract_id
}

output "group_name" {
  description = "returns a string"
  value       = data.akamai_group.this.group_name
}

output "id" {
  description = "returns a string"
  value       = data.akamai_group.this.id
}

output "name" {
  description = "returns a string"
  value       = data.akamai_group.this.name
}

output "this" {
  value = akamai_group.this
}
```

[top](#index)