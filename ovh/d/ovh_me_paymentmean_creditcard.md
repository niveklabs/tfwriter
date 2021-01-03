# ovh_me_paymentmean_creditcard

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_paymentmean_creditcard" {
  source = "./modules/ovh/d/ovh_me_paymentmean_creditcard"

  # description_regexp - (optional) is a type of string
  description_regexp = null
  # states - (optional) is a type of set of string
  states = []
  # use_default - (optional) is a type of bool
  use_default = null
  # use_last_to_expire - (optional) is a type of bool
  use_last_to_expire = null
}
```

[top](#index)

### Variables

```terraform
variable "description_regexp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "states" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "use_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_last_to_expire" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_paymentmean_creditcard" "this" {
  description_regexp = var.description_regexp
  states             = var.states
  use_default        = var.use_default
  use_last_to_expire = var.use_last_to_expire
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = data.ovh_me_paymentmean_creditcard.this.default
}

output "description" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_creditcard.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_creditcard.this.id
}

output "state" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_creditcard.this.state
}

output "this" {
  value = ovh_me_paymentmean_creditcard.this
}
```

[top](#index)