# equinix_network_account

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_account" {
  source = "./modules/equinix/d/equinix_network_account"

  # metro_code - (required) is a type of string
  metro_code = null
  # name - (optional) is a type of string
  name = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "metro_code" {
  description = "(required) - Account location metro cod"
  type        = string
}

variable "name" {
  description = "(optional) - Account name for filtering"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - Account status for filtering. Possible values are Active, Processing, Submitted, Staged"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_network_account" "this" {
  metro_code = var.metro_code
  name       = var.name
  status     = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.equinix_network_account.this.id
}

output "name" {
  description = "returns a string"
  value       = data.equinix_network_account.this.name
}

output "number" {
  description = "returns a string"
  value       = data.equinix_network_account.this.number
}

output "status" {
  description = "returns a string"
  value       = data.equinix_network_account.this.status
}

output "ucm_id" {
  description = "returns a string"
  value       = data.equinix_network_account.this.ucm_id
}

output "this" {
  value = equinix_network_account.this
}
```

[top](#index)