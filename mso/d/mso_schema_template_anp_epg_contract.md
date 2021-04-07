# mso_schema_template_anp_epg_contract

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
module "mso_schema_template_anp_epg_contract" {
  source = "./modules/mso/d/mso_schema_template_anp_epg_contract"

  # anp_name - (required) is a type of string
  anp_name = null
  # contract_name - (required) is a type of string
  contract_name = null
  # contract_schema_id - (optional) is a type of string
  contract_schema_id = null
  # contract_template_name - (optional) is a type of string
  contract_template_name = null
  # epg_name - (required) is a type of string
  epg_name = null
  # relationship_type - (optional) is a type of string
  relationship_type = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "anp_name" {
  description = "(required)"
  type        = string
}

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

variable "epg_name" {
  description = "(required)"
  type        = string
}

variable "relationship_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_anp_epg_contract" "this" {
  # anp_name - (required) is a type of string
  anp_name = var.anp_name
  # contract_name - (required) is a type of string
  contract_name = var.contract_name
  # contract_schema_id - (optional) is a type of string
  contract_schema_id = var.contract_schema_id
  # contract_template_name - (optional) is a type of string
  contract_template_name = var.contract_template_name
  # epg_name - (required) is a type of string
  epg_name = var.epg_name
  # relationship_type - (optional) is a type of string
  relationship_type = var.relationship_type
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # template_name - (required) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "contract_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg_contract.this.contract_schema_id
}

output "contract_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg_contract.this.contract_template_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg_contract.this.id
}

output "relationship_type" {
  description = "returns a string"
  value       = data.mso_schema_template_anp_epg_contract.this.relationship_type
}

output "this" {
  value = mso_schema_template_anp_epg_contract.this
}
```

[top](#index)