# akamai_appsec_configuration_version_clone

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
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_configuration_version_clone" {
  source = "./modules/akamai/r/akamai_appsec_configuration_version_clone"

  # config_id - (required) is a type of number
  config_id = null
  # create_from_version - (required) is a type of number
  create_from_version = null
  # rule_update - (optional) is a type of bool
  rule_update = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "create_from_version" {
  description = "(required)"
  type        = number
}

variable "rule_update" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_configuration_version_clone" "this" {
  config_id           = var.config_id
  create_from_version = var.create_from_version
  rule_update         = var.rule_update
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_configuration_version_clone.this.id
}

output "version" {
  description = "returns a number"
  value       = akamai_appsec_configuration_version_clone.this.version
}

output "this" {
  value = akamai_appsec_configuration_version_clone.this
}
```

[top](#index)