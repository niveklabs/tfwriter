# panos_panorama_ipsec_crypto_profile

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
module "panos_panorama_ipsec_crypto_profile" {
  source = "./modules/panos/r/panos_panorama_ipsec_crypto_profile"

  # authentications - (required) is a type of list of string
  authentications = []
  # dh_group - (optional) is a type of string
  dh_group = null
  # encryptions - (required) is a type of list of string
  encryptions = []
  # lifesize_type - (optional) is a type of string
  lifesize_type = null
  # lifesize_value - (optional) is a type of number
  lifesize_value = null
  # lifetime_type - (optional) is a type of string
  lifetime_type = null
  # lifetime_value - (optional) is a type of number
  lifetime_value = null
  # name - (required) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
}
```

[top](#index)

### Variables

```terraform
variable "authentications" {
  description = "(required)"
  type        = list(string)
}

variable "dh_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryptions" {
  description = "(required)"
  type        = list(string)
}

variable "lifesize_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifesize_value" {
  description = "(optional)"
  type        = number
  default     = null
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

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_ipsec_crypto_profile" "this" {
  authentications = var.authentications
  dh_group        = var.dh_group
  encryptions     = var.encryptions
  lifesize_type   = var.lifesize_type
  lifesize_value  = var.lifesize_value
  lifetime_type   = var.lifetime_type
  lifetime_value  = var.lifetime_value
  name            = var.name
  protocol        = var.protocol
  template        = var.template
  template_stack  = var.template_stack
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_ipsec_crypto_profile.this.id
}

output "this" {
  value = panos_panorama_ipsec_crypto_profile.this
}
```

[top](#index)