# akamai_appsec_configuration_rename

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
module "akamai_appsec_configuration_rename" {
  source = "./modules/akamai/r/akamai_appsec_configuration_rename"

  # config_id - (required) is a type of number
  config_id = null
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_configuration_rename" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_configuration_rename.this.id
}

output "this" {
  value = akamai_appsec_configuration_rename.this
}
```

[top](#index)