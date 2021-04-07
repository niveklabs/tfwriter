# panos_ike_crypto_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "panos_ike_crypto_profile" {
  source = "./modules/panos/r/panos_ike_crypto_profile"

  # authentication_multiple - (optional) is a type of number
  authentication_multiple = null
  # authentications - (required) is a type of list of string
  authentications = []
  # dh_groups - (required) is a type of list of string
  dh_groups = []
  # encryptions - (required) is a type of list of string
  encryptions = []
  # lifetime_type - (optional) is a type of string
  lifetime_type = null
  # lifetime_value - (optional) is a type of number
  lifetime_value = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "authentication_multiple" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authentications" {
  description = "(required)"
  type        = list(string)
}

variable "dh_groups" {
  description = "(required)"
  type        = list(string)
}

variable "encryptions" {
  description = "(required)"
  type        = list(string)
}

variable "lifetime_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifetime_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_ike_crypto_profile" "this" {
  # authentication_multiple - (optional) is a type of number
  authentication_multiple = var.authentication_multiple
  # authentications - (required) is a type of list of string
  authentications = var.authentications
  # dh_groups - (required) is a type of list of string
  dh_groups = var.dh_groups
  # encryptions - (required) is a type of list of string
  encryptions = var.encryptions
  # lifetime_type - (optional) is a type of string
  lifetime_type = var.lifetime_type
  # lifetime_value - (optional) is a type of number
  lifetime_value = var.lifetime_value
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ike_crypto_profile.this.id
}

output "this" {
  value = panos_ike_crypto_profile.this
}
```

[top](#index)