# akamai_appsec_configuration

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
module "akamai_appsec_configuration" {
  source = "./modules/akamai/d/akamai_appsec_configuration"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_configuration" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "config_id" {
  description = "returns a number"
  value       = data.akamai_appsec_configuration.this.config_id
}

output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration.this.id
}

output "latest_version" {
  description = "returns a number"
  value       = data.akamai_appsec_configuration.this.latest_version
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_configuration.this.output_text
}

output "production_version" {
  description = "returns a number"
  value       = data.akamai_appsec_configuration.this.production_version
}

output "staging_version" {
  description = "returns a number"
  value       = data.akamai_appsec_configuration.this.staging_version
}

output "this" {
  value = akamai_appsec_configuration.this
}
```

[top](#index)