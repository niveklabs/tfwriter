# ovh_me_paymentmean_bankaccount

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
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_paymentmean_bankaccount" {
  source = "./modules/ovh/d/ovh_me_paymentmean_bankaccount"

  # description_regexp - (optional) is a type of string
  description_regexp = null
  # state - (optional) is a type of string
  state = null
  # use_default - (optional) is a type of bool
  use_default = null
  # use_oldest - (optional) is a type of bool
  use_oldest = null
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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_oldest" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_me_paymentmean_bankaccount" "this" {
  description_regexp = var.description_regexp
  state              = var.state
  use_default        = var.use_default
  use_oldest         = var.use_oldest
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = data.ovh_me_paymentmean_bankaccount.this.default
}

output "description" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_bankaccount.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_bankaccount.this.id
}

output "state" {
  description = "returns a string"
  value       = data.ovh_me_paymentmean_bankaccount.this.state
}

output "this" {
  value = ovh_me_paymentmean_bankaccount.this
}
```

[top](#index)