# akamai_contract

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
module "akamai_contract" {
  source = "./modules/akamai/d/akamai_contract"

  # group - (optional) is a type of string
  group = null
  # group_id - (optional) is a type of string
  group_id = null
  # group_name - (optional) is a type of string
  group_name = null
}
```

[top](#index)

### Variables

```terraform
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

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_contract" "this" {
  group      = var.group
  group_id   = var.group_id
  group_name = var.group_name
}
```

[top](#index)

### Outputs

```terraform
output "group_id" {
  description = "returns a string"
  value       = data.akamai_contract.this.group_id
}

output "group_name" {
  description = "returns a string"
  value       = data.akamai_contract.this.group_name
}

output "id" {
  description = "returns a string"
  value       = data.akamai_contract.this.id
}

output "this" {
  value = akamai_contract.this
}
```

[top](#index)