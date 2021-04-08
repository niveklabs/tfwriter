# vmc_connected_accounts

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_connected_accounts" {
  source = "./modules/vmc/d/vmc_connected_accounts"

  # account_number - (required) is a type of string
  account_number = null
  # provider_type - (optional) is a type of string
  provider_type = null
}
```

[top](#index)

### Variables

```terraform
variable "account_number" {
  description = "(required) - AWS account number."
  type        = string
}

variable "provider_type" {
  description = "(optional) - The cloud provider of the SDDC (AWS or ZeroCloud)."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vmc_connected_accounts" "this" {
  # account_number - (required) is a type of string
  account_number = var.account_number
  # provider_type - (optional) is a type of string
  provider_type = var.provider_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vmc_connected_accounts.this.id
}

output "this" {
  value = vmc_connected_accounts.this
}
```

[top](#index)