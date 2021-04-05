# panos_data_filtering_security_profiles

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
module "panos_data_filtering_security_profiles" {
  source = "./modules/panos/d/panos_data_filtering_security_profiles"

  # device_group - (optional) is a type of string
  device_group = null
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

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_data_filtering_security_profiles" "this" {
  device_group = var.device_group
  vsys         = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_data_filtering_security_profiles.this.id
}

output "listing" {
  description = "returns a list of string"
  value       = data.panos_data_filtering_security_profiles.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.panos_data_filtering_security_profiles.this.total
}

output "this" {
  value = panos_data_filtering_security_profiles.this
}
```

[top](#index)