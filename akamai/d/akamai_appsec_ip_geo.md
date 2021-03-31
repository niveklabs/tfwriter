# akamai_appsec_ip_geo

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
module "akamai_appsec_ip_geo" {
  source = "./modules/akamai/d/akamai_appsec_ip_geo"

  # config_id - (required) is a type of number
  config_id = null
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

### Datasource

```terraform
data "akamai_appsec_ip_geo" "this" {
  config_id          = var.config_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "exception_ip_network_lists" {
  description = "returns a set of string"
  value       = data.akamai_appsec_ip_geo.this.exception_ip_network_lists
}

output "geo_network_lists" {
  description = "returns a set of string"
  value       = data.akamai_appsec_ip_geo.this.geo_network_lists
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_ip_geo.this.id
}

output "ip_network_lists" {
  description = "returns a set of string"
  value       = data.akamai_appsec_ip_geo.this.ip_network_lists
}

output "mode" {
  description = "returns a string"
  value       = data.akamai_appsec_ip_geo.this.mode
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_ip_geo.this.output_text
}

output "this" {
  value = akamai_appsec_ip_geo.this
}
```

[top](#index)