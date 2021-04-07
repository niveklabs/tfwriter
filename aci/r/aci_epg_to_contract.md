# aci_epg_to_contract

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_epg_to_contract" {
  source = "./modules/aci/r/aci_epg_to_contract"

  # annotation - (optional) is a type of string
  annotation = null
  # application_epg_dn - (required) is a type of string
  application_epg_dn = null
  # contract_dn - (required) is a type of string
  contract_dn = null
  # contract_type - (required) is a type of string
  contract_type = null
  # description - (optional) is a type of string
  description = null
  # match_t - (optional) is a type of string
  match_t = null
  # prio - (optional) is a type of string
  prio = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_epg_dn" {
  description = "(required)"
  type        = string
}

variable "contract_dn" {
  description = "(required)"
  type        = string
}

variable "contract_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_t" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_epg_to_contract" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # application_epg_dn - (required) is a type of string
  application_epg_dn = var.application_epg_dn
  # contract_dn - (required) is a type of string
  contract_dn = var.contract_dn
  # contract_type - (required) is a type of string
  contract_type = var.contract_type
  # description - (optional) is a type of string
  description = var.description
  # match_t - (optional) is a type of string
  match_t = var.match_t
  # prio - (optional) is a type of string
  prio = var.prio
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_epg_to_contract.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_epg_to_contract.this.id
}

output "match_t" {
  description = "returns a string"
  value       = aci_epg_to_contract.this.match_t
}

output "prio" {
  description = "returns a string"
  value       = aci_epg_to_contract.this.prio
}

output "this" {
  value = aci_epg_to_contract.this
}
```

[top](#index)