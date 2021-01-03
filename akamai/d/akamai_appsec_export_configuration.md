# akamai_appsec_export_configuration

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
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_export_configuration" {
  source = "./modules/akamai/d/akamai_appsec_export_configuration"

  # config_id - (required) is a type of number
  config_id = null
  # search - (optional) is a type of list of string
  search = []
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

variable "search" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "akamai_appsec_export_configuration" "this" {
  config_id = var.config_id
  search    = var.search
  version   = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_export_configuration.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_export_configuration.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_export_configuration.this.output_text
}

output "this" {
  value = akamai_appsec_export_configuration.this
}
```

[top](#index)