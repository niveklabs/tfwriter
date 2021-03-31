# akamai_appsec_configuration

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
module "akamai_appsec_configuration" {
  source = "./modules/akamai/r/akamai_appsec_configuration"

  # contract_id - (required) is a type of string
  contract_id = null
  # description - (required) is a type of string
  description = null
  # group_id - (required) is a type of number
  group_id = null
  # host_names - (required) is a type of list of string
  host_names = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = number
}

variable "host_names" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_configuration" "this" {
  contract_id = var.contract_id
  description = var.description
  group_id    = var.group_id
  host_names  = var.host_names
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "config_id" {
  description = "returns a number"
  value       = akamai_appsec_configuration.this.config_id
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_configuration.this.id
}

output "version" {
  description = "returns a number"
  value       = akamai_appsec_configuration.this.version
}

output "this" {
  value = akamai_appsec_configuration.this
}
```

[top](#index)