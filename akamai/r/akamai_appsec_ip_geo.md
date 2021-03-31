# akamai_appsec_ip_geo

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "akamai_appsec_ip_geo" {
  source = "./modules/akamai/r/akamai_appsec_ip_geo"

  # config_id - (required) is a type of number
  config_id = null
  # exception_ip_network_lists - (optional) is a type of set of string
  exception_ip_network_lists = []
  # geo_network_lists - (optional) is a type of set of string
  geo_network_lists = []
  # ip_network_lists - (optional) is a type of set of string
  ip_network_lists = []
  # mode - (required) is a type of string
  mode = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "exception_ip_network_lists" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "geo_network_lists" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ip_network_lists" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "security_policy_id" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_ip_geo" "this" {
  config_id                  = var.config_id
  exception_ip_network_lists = var.exception_ip_network_lists
  geo_network_lists          = var.geo_network_lists
  ip_network_lists           = var.ip_network_lists
  mode                       = var.mode
  security_policy_id         = var.security_policy_id
  version                    = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_ip_geo.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_ip_geo.this.output_text
}

output "this" {
  value = akamai_appsec_ip_geo.this
}
```

[top](#index)