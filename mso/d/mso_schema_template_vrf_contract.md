# mso_schema_template_vrf_contract

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_vrf_contract" {
  source = "./modules/mso/d/mso_schema_template_vrf_contract"

  # contract_name - (required) is a type of string
  contract_name = null
  # contract_schema_id - (optional) is a type of string
  contract_schema_id = null
  # contract_template_name - (optional) is a type of string
  contract_template_name = null
  # relationship_type - (required) is a type of string
  relationship_type = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vrf_name - (required) is a type of string
  vrf_name = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_name" {
  description = "(required)"
  type        = string
}

variable "contract_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relationship_type" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vrf_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_vrf_contract" "this" {
  # contract_name - (required) is a type of string
  contract_name = var.contract_name
  # contract_schema_id - (optional) is a type of string
  contract_schema_id = var.contract_schema_id
  # contract_template_name - (optional) is a type of string
  contract_template_name = var.contract_template_name
  # relationship_type - (required) is a type of string
  relationship_type = var.relationship_type
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # template_name - (required) is a type of string
  template_name = var.template_name
  # vrf_name - (required) is a type of string
  vrf_name = var.vrf_name
}
```

[top](#index)

### Outputs

```terraform
output "contract_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_vrf_contract.this.contract_schema_id
}

output "contract_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_vrf_contract.this.contract_template_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_vrf_contract.this.id
}

output "this" {
  value = mso_schema_template_vrf_contract.this
}
```

[top](#index)