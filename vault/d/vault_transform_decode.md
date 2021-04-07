# vault_transform_decode

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_transform_decode" {
  source = "./modules/vault/d/vault_transform_decode"

  # batch_input - (optional) is a type of list of map of string
  batch_input = [{}]
  # batch_results - (optional) is a type of list of map of string
  batch_results = [{}]
  # decoded_value - (optional) is a type of string
  decoded_value = null
  # path - (required) is a type of string
  path = null
  # role_name - (required) is a type of string
  role_name = null
  # transformation - (optional) is a type of string
  transformation = null
  # tweak - (optional) is a type of string
  tweak = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "batch_input" {
  description = "(optional) - Specifies a list of items to be decoded in a single batch. If this parameter is set, the top-level parameters 'value', 'transformation' and 'tweak' will be ignored. Each batch item within the list can specify these parameters instead."
  type        = list(map(string))
  default     = null
}

variable "batch_results" {
  description = "(optional) - The result of decoding batch_input."
  type        = list(map(string))
  default     = null
}

variable "decoded_value" {
  description = "(optional) - The result of decoding a value."
  type        = string
  default     = null
}

variable "path" {
  description = "(required) - Path to backend from which to retrieve data."
  type        = string
}

variable "role_name" {
  description = "(required) - The name of the role."
  type        = string
}

variable "transformation" {
  description = "(optional) - The transformation to perform. If no value is provided and the role contains a single transformation, this value will be inferred from the role."
  type        = string
  default     = null
}

variable "tweak" {
  description = "(optional) - The tweak value to use. Only applicable for FPE transformations"
  type        = string
  default     = null
}

variable "value" {
  description = "(optional) - The value in which to decode."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_transform_decode" "this" {
  # batch_input - (optional) is a type of list of map of string
  batch_input = var.batch_input
  # batch_results - (optional) is a type of list of map of string
  batch_results = var.batch_results
  # decoded_value - (optional) is a type of string
  decoded_value = var.decoded_value
  # path - (required) is a type of string
  path = var.path
  # role_name - (required) is a type of string
  role_name = var.role_name
  # transformation - (optional) is a type of string
  transformation = var.transformation
  # tweak - (optional) is a type of string
  tweak = var.tweak
  # value - (optional) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "batch_results" {
  description = "returns a list of map of string"
  value       = data.vault_transform_decode.this.batch_results
}

output "decoded_value" {
  description = "returns a string"
  value       = data.vault_transform_decode.this.decoded_value
}

output "id" {
  description = "returns a string"
  value       = data.vault_transform_decode.this.id
}

output "this" {
  value = vault_transform_decode.this
}
```

[top](#index)