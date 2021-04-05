# panos_wildfire_analysis_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_wildfire_analysis_security_profile" {
  source = "./modules/panos/d/panos_wildfire_analysis_security_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_wildfire_analysis_security_profile" "this" {
  device_group = var.device_group
  name         = var.name
  vsys         = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.panos_wildfire_analysis_security_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.panos_wildfire_analysis_security_profile.this.id
}

output "rule" {
  description = "returns a list of object"
  value       = data.panos_wildfire_analysis_security_profile.this.rule
}

output "this" {
  value = panos_wildfire_analysis_security_profile.this
}
```

[top](#index)