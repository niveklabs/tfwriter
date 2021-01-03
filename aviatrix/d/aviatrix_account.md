# aviatrix_account

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_account" {
  source = "./modules/aviatrix/d/aviatrix_account"

  # account_name - (required) is a type of string
  account_name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name. This can be used for logging in to CloudN console or UserConnect controller."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_account" "this" {
  account_name = var.account_name
}
```

[top](#index)

### Outputs

```terraform
output "aws_access_key" {
  description = "returns a string"
  value       = data.aviatrix_account.this.aws_access_key
}

output "aws_account_number" {
  description = "returns a string"
  value       = data.aviatrix_account.this.aws_account_number
}

output "aws_role_arn" {
  description = "returns a string"
  value       = data.aviatrix_account.this.aws_role_arn
}

output "aws_role_ec2" {
  description = "returns a string"
  value       = data.aviatrix_account.this.aws_role_ec2
}

output "cloud_type" {
  description = "returns a number"
  value       = data.aviatrix_account.this.cloud_type
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_account.this.id
}

output "this" {
  value = aviatrix_account.this
}
```

[top](#index)