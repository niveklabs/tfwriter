# akamai_appsec_contracts_groups

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
module "akamai_appsec_contracts_groups" {
  source = "./modules/akamai/d/akamai_appsec_contracts_groups"

  # contractid - (optional) is a type of string
  contractid = null
  # groupid - (optional) is a type of number
  groupid = null
}
```

[top](#index)

### Variables

```terraform
variable "contractid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groupid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_contracts_groups" "this" {
  # contractid - (optional) is a type of string
  contractid = var.contractid
  # groupid - (optional) is a type of number
  groupid = var.groupid
}
```

[top](#index)

### Outputs

```terraform
output "default_contractid" {
  description = "returns a string"
  value       = data.akamai_appsec_contracts_groups.this.default_contractid
}

output "default_groupid" {
  description = "returns a number"
  value       = data.akamai_appsec_contracts_groups.this.default_groupid
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_contracts_groups.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_contracts_groups.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_contracts_groups.this.output_text
}

output "this" {
  value = akamai_appsec_contracts_groups.this
}
```

[top](#index)