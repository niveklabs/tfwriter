# aviatrix_aws_guard_duty

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_aws_guard_duty" {
  source = "./modules/aviatrix/r/aviatrix_aws_guard_duty"

  # account_name - (required) is a type of string
  account_name = null
  # excluded_ips - (optional) is a type of set of string
  excluded_ips = []
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - Account name"
  type        = string
}

variable "excluded_ips" {
  description = "(optional) - Excluded IPs."
  type        = set(string)
  default     = null
}

variable "region" {
  description = "(required) - Region."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_aws_guard_duty" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # excluded_ips - (optional) is a type of set of string
  excluded_ips = var.excluded_ips
  # region - (required) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_aws_guard_duty.this.id
}

output "this" {
  value = aviatrix_aws_guard_duty.this
}
```

[top](#index)