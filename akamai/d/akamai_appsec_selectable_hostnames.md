# akamai_appsec_selectable_hostnames

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
module "akamai_appsec_selectable_hostnames" {
  source = "./modules/akamai/d/akamai_appsec_selectable_hostnames"

  # active_in_production - (optional) is a type of bool
  active_in_production = null
  # active_in_staging - (optional) is a type of bool
  active_in_staging = null
  # config_id - (optional) is a type of number
  config_id = null
  # contractid - (optional) is a type of string
  contractid = null
  # groupid - (optional) is a type of number
  groupid = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "active_in_production" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "active_in_staging" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "config_id" {
  description = "(optional)"
  type        = number
  default     = null
}

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

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_selectable_hostnames" "this" {
  active_in_production = var.active_in_production
  active_in_staging    = var.active_in_staging
  config_id            = var.config_id
  contractid           = var.contractid
  groupid              = var.groupid
  version              = var.version
}
```

[top](#index)

### Outputs

```terraform
output "hostnames" {
  description = "returns a list of string"
  value       = data.akamai_appsec_selectable_hostnames.this.hostnames
}

output "hostnames_json" {
  description = "returns a string"
  value       = data.akamai_appsec_selectable_hostnames.this.hostnames_json
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_selectable_hostnames.this.id
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_selectable_hostnames.this.output_text
}

output "this" {
  value = akamai_appsec_selectable_hostnames.this
}
```

[top](#index)