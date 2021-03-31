# equinix_ecx_l2_sellerprofiles

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_sellerprofiles" {
  source = "./modules/equinix/d/equinix_ecx_l2_sellerprofiles"

  # metro_codes - (optional) is a type of set of string
  metro_codes = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # organization_global_name - (optional) is a type of string
  organization_global_name = null
  # organization_name - (optional) is a type of string
  organization_name = null
  # speed_bands - (optional) is a type of set of string
  speed_bands = []
}
```

[top](#index)

### Variables

```terraform
variable "metro_codes" {
  description = "(optional) - List of metro codes of locations that should be served by resulting profiles"
  type        = set(string)
  default     = null
}

variable "name_regex" {
  description = "(optional) - A regex string to apply on returned seller profile names and filter search results"
  type        = string
  default     = null
}

variable "organization_global_name" {
  description = "(optional) - Name of seller's global organization"
  type        = string
  default     = null
}

variable "organization_name" {
  description = "(optional) - Name of seller's organization"
  type        = string
  default     = null
}

variable "speed_bands" {
  description = "(optional) - List of speed bands that should be supported by resulting profiles"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_ecx_l2_sellerprofiles" "this" {
  metro_codes              = var.metro_codes
  name_regex               = var.name_regex
  organization_global_name = var.organization_global_name
  organization_name        = var.organization_name
  speed_bands              = var.speed_bands
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofiles.this.id
}

output "profiles" {
  description = "returns a list of object"
  value       = data.equinix_ecx_l2_sellerprofiles.this.profiles
}

output "this" {
  value = equinix_ecx_l2_sellerprofiles.this
}
```

[top](#index)