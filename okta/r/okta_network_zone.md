# okta_network_zone

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_network_zone" {
  source = "./modules/okta/r/okta_network_zone"

  # dynamic_locations - (optional) is a type of set of string
  dynamic_locations = []
  # gateways - (optional) is a type of set of string
  gateways = []
  # name - (required) is a type of string
  name = null
  # proxies - (optional) is a type of set of string
  proxies = []
  # type - (required) is a type of string
  type = null
  # usage - (optional) is a type of string
  usage = null
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_locations" {
  description = "(optional) - Array of locations ISO-3166-1(2). Format code: countryCode OR countryCode-regionCode"
  type        = set(string)
  default     = null
}

variable "gateways" {
  description = "(optional) - Array of values in CIDR/range form depending on the way it's been declared (i.e. CIDR will contain /suffix). Please check API docs for examples"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the Network Zone Resource"
  type        = string
}

variable "proxies" {
  description = "(optional) - Array of values in CIDR/range form depending on the way it's been declared (i.e. CIDR will contain /suffix). Please check API docs for examples"
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(required) - Type of the Network Zone - can either be IP or DYNAMIC only"
  type        = string
}

variable "usage" {
  description = "(optional) - Zone's purpose: POLICY or BLOCKLIST"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_network_zone" "this" {
  # dynamic_locations - (optional) is a type of set of string
  dynamic_locations = var.dynamic_locations
  # gateways - (optional) is a type of set of string
  gateways = var.gateways
  # name - (required) is a type of string
  name = var.name
  # proxies - (optional) is a type of set of string
  proxies = var.proxies
  # type - (required) is a type of string
  type = var.type
  # usage - (optional) is a type of string
  usage = var.usage
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_network_zone.this.id
}

output "this" {
  value = okta_network_zone.this
}
```

[top](#index)