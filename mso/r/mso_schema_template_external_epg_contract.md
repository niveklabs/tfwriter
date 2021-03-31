# mso_schema_template_external_epg_contract

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "mso_schema_template_external_epg_contract" {
  source = "./modules/mso/r/mso_schema_template_external_epg_contract"

  # contract_name - (required) is a type of string
  contract_name = null
  # contract_schema_id - (optional) is a type of string
  contract_schema_id = null
  # contract_template_name - (optional) is a type of string
  contract_template_name = null
  # external_epg_name - (required) is a type of string
  external_epg_name = null
  # relationship_type - (required) is a type of string
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

variable "external_epg_name" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "mso_schema_template_external_epg_contract" "this" {
  contract_name          = var.contract_name
  contract_schema_id     = var.contract_schema_id
  contract_template_name = var.contract_template_name
  external_epg_name      = var.external_epg_name
  relationship_type      = var.relationship_type
  schema_id              = var.schema_id
  template_name          = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "contract_schema_id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg_contract.this.contract_schema_id
}

output "contract_template_name" {
  description = "returns a string"
  value       = mso_schema_template_external_epg_contract.this.contract_template_name
}

output "id" {
  description = "returns a string"
  value       = mso_schema_template_external_epg_contract.this.id
}

output "this" {
  value = mso_schema_template_external_epg_contract.this
}
```

[top](#index)