# akamai_appsec_configuration_version

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
module "akamai_appsec_configuration_version" {
  source = "./modules/akamai/d/akamai_appsec_configuration_version"

  # config_id - (required) is a type of number
  config_id = null
  # version - (optional) is a type of number
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

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_configuration_version" "this" {
  config_id = var.config_id
  version   = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration_version.this.id
}

output "latest_version" {
  description = "returns a number"
  value       = data.akamai_appsec_configuration_version.this.latest_version
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration_version.this.output_text
}

output "production_status" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration_version.this.production_status
}

output "staging_status" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration_version.this.staging_status
}

output "this" {
  value = akamai_appsec_configuration_version.this
}
```

[top](#index)