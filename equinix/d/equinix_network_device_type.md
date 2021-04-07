# equinix_network_device_type

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
module "equinix_network_device_type" {
  source = "./modules/equinix/d/equinix_network_device_type"

  # category - (optional) is a type of string
  category = null
  # metro_codes - (optional) is a type of set of string
  metro_codes = []
  # name - (optional) is a type of string
  name = null
  # vendor - (optional) is a type of string
  vendor = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional) - Device type category, one of: Router, Firewall, SDWAN"
  type        = string
  default     = null
}

variable "metro_codes" {
  description = "(optional) - List of metro codes where device type has to be available"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(optional) - Device type name"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional) - Device type vendor i.e. Cisco, Juniper Networks, VERSA Networks"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_network_device_type" "this" {
  # category - (optional) is a type of string
  category = var.category
  # metro_codes - (optional) is a type of set of string
  metro_codes = var.metro_codes
  # name - (optional) is a type of string
  name = var.name
  # vendor - (optional) is a type of string
  vendor = var.vendor
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.category
}

output "code" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.code
}

output "description" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.description
}

output "id" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.id
}

output "metro_codes" {
  description = "returns a set of string"
  value       = data.equinix_network_device_type.this.metro_codes
}

output "name" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.name
}

output "vendor" {
  description = "returns a string"
  value       = data.equinix_network_device_type.this.vendor
}

output "this" {
  value = equinix_network_device_type.this
}
```

[top](#index)